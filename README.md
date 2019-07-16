# Mini Project - 

Worked on encoding and decoding text files in images and consequently setting up an HTTP based client server application.





## Instructions for Encoding

1. Run MyServer.py
2. Go to localhost:55555 and you'll get a 400 Bad Request response since this request is not programmed to do anything as per the API
3. Go to localhost:55555/file1.txt to recieve the contents of file1 encoded into a random image from the 5 present in the project directory
4. Save the encoded image file. Make sure to select right file type (i.e. png) while saving
5. You can fetch any of the ten files (from file1.txt to file10.txt). But fetching a file that is not present in the directory (i.e. file50 for example) will result in a 404 Not Found response


## Instructions for Decoding

1. Copy the encoded image to the project root
2. Open Decoder.py and set the variable imageName to the name of the encoded image file.
3. Run the script and you'll see the decoded text

## Project Status

1. Server sends appropriate HTTP response messages
2. Server is able to encode any text file (from the 10 available) into an image (randomly chosen from the 5 24-bit PNGs available)
3. Server is able to serve the client with the encoded image
4. Client is able to open the image into any image editing software
5. There are no visual differences between the encoded image and the original image
6. An independent script is provided for anyone to decode the encoded image

## Project Performance

- In one benchmarking test, encoding a complete book of 492KB into an image of 3.2MB took around 7 seconds and the decoding took around 6 seconds.
- It has been ensured that the algorithm is able to encode all ASCII characters. And during testing, various text files of various sizes have been encoded into several distinct images to ensure a bug free program.
- To improve the algorithm's performance, bit hacks have been employed in all three cases of fetching/setting/clearing the LSB of a byte.
- It has been ensured that every byte of an image is encoded with one bit of data. So, three pixels of an image are being used for encoding one byte of data.
- A regular expression is used for fetching the number of file requested by client
- The binary of text to be encoded is terminated with bits 10000000000… so the decoder knows when to stop. It has been ensured that this technique works well. In fact, a sequence like 000000000000… would’ve caused severe bugs in the program. But we’ve started our sequence with a 1 and have then proceeded it with several dozen zeros.

## Project Dependencies

The project has been built using Python 3.5. Other external libraries used in the project
are: Socket, Sys, RE, OS, Random, Binascii & Pillow.

