# What is Stream?

Stream in Node.js simply means a sequence of data being moved from one point to the other over time. The whole concept is, you have a huge amount of data to process, but you don’t need to wait for all the data to be available before you start processing it.

Basically, this big data is broken down and sent in chunks. So from the original definition of a buffer (“streams of binary data… in the context of… file system”) this simply means binary data being moved in the file system.**For example**, moving the texts stored in file1.txt to file2.txt.

## Stream Benefits:

* No need to wait for the entire resource to load.
* abstraction for continuous chunking of data.
* If you are absolutely sure that your all of your data fits in a single chunk, there is no immediate benefit to using streams.
* you can configure the chunk size
* You can pipe a single readable stream into multiple writable streams which would be a pain to do using only asynchronous callback
* low memory footprint
* buffers allow you to work around the v8 heap memory limit



## Stream is Used In:
* HTTP request & responses
* Standard input/output(stdin & stdout)
* File reads and write


# What is Buffer?

We’ve seen that a stream of data is the movement of data from one point to the other, but how exactly are they moved?

Typically, the movement of data is usually with the intention to process it, or read it, and make decisions based on it. But there is a minimum and a maximum amount of data a process could take over time. So if the rate the data arrives is faster than the rate the process consumes the data, the excess data need to wait somewhere for its turn to be processed.

On the other hand, if the process is consuming the data faster than it arrives, the few data that arrive earlier need to wait for a certain amount of data to arrive before being sent out for processing.


## Interacting with a Buffer:


It is even possible to create your own buffer! Aside from the one Node.js will automatically create during a stream, it is possible to create and manipulate your own buffer. Interesting right? Let’s create one!

Depending on what you want to achieve, there are different ways to create a buffer. Let’s see some.
~~~~
// Create an empty buffer of size 10.
// A buffer that only can accommodate 10 bytes.
const buf1 = Buffer.alloc(10);
// Create a buffer with content
const buf2 = Buffer.from("hello buffer");
~~~~

Once your buffer has been created, you can start interacting with it

~~~~
// Examine the structure of a buffer
buf1.toJSON()
// { type: 'Buffer', data: [ 0, 0, 0, 0, 0, 0, 0, 0, 0, 0 ] }
// an empty buffer
buf2.toJSON()
// { type: 'Buffer',
     data: [
       104, 101, 108, 108, 111, 32, 98, 117, 102, 102, 101, 114
     ]
   }
// the toJSON() method presents the data as the Unicode Code Points of the characters
// Examine the size of a buffer
buf1.length // 10
buf2.length // 12. Auto-assigned based on the initial content when created.
// Write to a buffer
buf1.write("Buffer really rocks!")

// Decode a buffer
buf1.toString() // 'Buffer rea'
//oops, because buf1 is created to contain only 10 bytes, it couldn't accommodate the rest of the characters
// Compare two buffers
~~~~

![alt text](https://cdn-images-1.medium.com/max/1040/1*lhOvZiDrVbzF8_l8QX3ACw.png)


## How to use streams

fs.readfile: Reads the file specified (take space for the file in memory)

fs.createReadStream: this will read the file as chunks
~~~~
var fs = require('fs');
var rstream = fs.createReadStream('./data.txt')

rstream.on('open', function () {
    rstream.pipe(process.stdout);
}
~~~~
