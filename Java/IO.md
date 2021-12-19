### What are the types of I / O streams?
ByteStream(8 bits) and CharacterStream(16 bits).

ByteStream are used for not text or not english. The base class InputStream represents classes that receive data from various sources. The class OutputStream is an abstract class that defines stream byte output. 

We can simplify the stream code with try with resources.

Character streams have two main abstract classes, Reader and Writer , which control the flow of Unicode characters. The Reader class is an abstract class that defines character streaming input. The Writer class is an abstract class that defines character stream output. In case of errors, all class methods throw an IOException.

### When to use Character Stream over Byte Stream? 
characters are stored using Unicode conventions. Character stream is useful when we want to process text files. These text files can be processed character by character. A character size is typically 16 bits.

#### When to use Byte Stream over Character Stream? 
Byte oriented reads byte by byte. A byte stream is suitable for processing raw data like binary files.

#### The IO is really expensive to use so how can we reduce the number of interaction between software and hardware
load all of them ot memory at one time, use buffer

#### flush()
Flushes the output stream and forces any buffered output bytes to be written out.

#### It's not serialization
Serialization uses ObjectInputStream/ObjectOutputStream

#### transfer API 
TransferTo() belong to InputStream
