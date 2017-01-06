# tube-hacked-junior
Guess the secret code to broadcast your YouTube video to the whole room!

### How to play
Make an HTTP POST request with your guess and the ID code to any YouTube video to our server's address, and if your guess is correct, the page will celebrate your victory and play the video.
(The ID code is the bit at the end of the YouTube URL after the equals sign.)

#### Why is that equals sign there in the first place?
URL encoding is a way to link key-value pairs in plain text, like in the URL bar of a browser. 

### HTTP requests in Python
Python provides a native module that includes functions for creating connections and building HTTP requests. Research how to use these in the Python docs.

### Stretch goals
Our server is written in JavaScript--how would you make a Python HTTP server that does the same thing? It needs to be able to recieve and interpret HTTP requests from clients and send an appropriate response based on the request's content.
