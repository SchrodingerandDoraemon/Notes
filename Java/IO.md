#### Q1. What are the types of I / O streams?
ByteStream(8 bits) and CharacterStream(16 bits).

ByteStream are used for not text or not english

We can simplify the stream code with try with resources.

#### The IO is really expensive to use so how can we reduce the number of interaction between software and hardware
load all of them ot memory at one time, use buffer

#### flush()
Flushes the output stream and forces any buffered output bytes to be written out.

#### It's not serialization
Serialization uses ObjectInputStream/ObjectOutputStream

#### transfer API 
TransferTo() belong to InputStream
