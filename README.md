# Compression bug

To reproduce:

- make sure you're using Java 11
- ./gradlew bootRun

Then open a browser, open the Network dev tools and go to `http://localhost:8080`.

Notice that the response for `style-4ce1c5e82f39cb76e3192de253984c16.css` and for `bundle.js`
are compressed, but not the response for `bundle-c525abb80dc9c078dce19f0c5422994a.js`.

This is noticeable by compraring the size of the file with the trasnferred size, or 
by displaying the response headers and seeing that `Content-Encoding: gzip` is not set
for `bundle-c525abb80dc9c078dce19f0c5422994a.js`.
