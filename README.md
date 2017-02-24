# Assignment-4.4

1. DFSInputStream

It is responsible for storing the data node adresses of the first few blocks of the file that is needed by the client. When the end of the block is reached, it will close the connection to the datanode, then find the best datanode for the next block of the file. It handles integrity of data contained by the blocks and Manages data read activity in case of datanode failure.

2. DFSOutputStream

DFSOutputStream creates files from a stream of bytes. The client application writes data that is cached internally by this stream.A packet comprises of chunks. Each chunk is typically 512 bytes and has an associated checksum with it. When a client application fills up the currentPacket, it is enqueued into dataQueue.The data queue is consumed by the DataStreamer, whose responsibility it is to ask the namenode to allocate new blocks by picking a list of suitable datanodes to store the replicas.

3. FSDataInputStream
The open() method on FileSystem actually returns a FSDataInputStream rather than a standard java.io class. This class is a specialization of java.io.DataInputStream with support for random access, so you can read from any part of the stream. 

4. FSDataOutputStream
The client creates the file by calling create() method on DistributedFileSystem. it makes an RPC call to the namenode to create a new file in the filesystem’s namespace, with no blocks associated with it.
