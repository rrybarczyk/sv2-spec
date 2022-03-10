# Framing
The protocol is binary, with fixed message framing.
Each message begins with the extension type, message type, and message length (six bytes in total), followed by a variable length message.
The message framing is outlined below:

```
+----------------+-------------+---------------------------------------------------------------------------------------+
| Protocol Type  | Byte Length | Description                                                                           |
+----------------+-------------+---------------------------------------------------------------------------------------+
| extension_type | U16         | Unique identifier of the extension describing this protocol message.                  |
|                |             |                                                                                       |
|                |             | Most significant bit (i.e.bit 15, 0-indexed, aka channel_msg) indicates a message     |
|                |             | which is specific to a channel, whereas if the most significant bit is unset, the     |
|                |             | message is to be interpreted by the immediate receiving device.                       |
|                |             |                                                                                       |
|                |             | Note that the channel_msg bit is ignored in the extension lookup, i.e.an              |
|                |             | extension_type of 0x8ABC is for the same "extension" as 0x0ABC.                       |
|                |             |                                                                                       |
|                |             | If the channel_msg bit is set, the first four bytes of the payload field is a U32     |
|                |             | representing the channel_id this message is destined for (these bytes are repeated in |
|                |             | the message framing descriptions below).                                              |
|                |             |                                                                                       |
|                |             | Note that for the Job Negotiation and Template Distribution Protocols the channel_msg |
|                |             | bit is always unset.                                                                  |
+----------------+-------------+---------------------------------------------------------------------------------------+
| msg_type       | U8          | Unique identifier of the extension describing this protocol message.                  |
+----------------+-------------+---------------------------------------------------------------------------------------+
| msg_length     | U24         | Length of the protocol message, not including this header.                            |
+----------------+-------------+---------------------------------------------------------------------------------------+
| payload        | BYTES       | Message-specific payload of length msg_length. If the MSB in extension_type           |
|                |             | (the channel_msg bit) is set the first four bytes are defined as a U32 "channel_id",  |
|                |             | though this definition is repeated in the message definitions below and these 4 bytes |
|                |             | are included in msg_length.                                                           |
+----------------+-------------+---------------------------------------------------------------------------------------+

```
