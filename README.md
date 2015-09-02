TiQRCode
========

This is a titaniumified version of [Jacek Siciarek's QR code generator](https://github.com/siciarek/javascript-qrcode).  This module returns only the data matrix und this matrix you can use in rendering programms.


Usage
-----


Example for usage inside jspdf:
~~~
var PADDING = 5;
var qrcode = new (require('de.appwerft.qrcode'))('http://google.com','M');
var code = qrcode.getData();  // matrix of '0's' and '1's'
var R = width / qrcode.getSize();   // calculating of raster
doc.setDrawColor(color);  // pdf syntax, i.e. 0 for black
doc.setFillColor(color);
for (var r = 0; r < code.length; r += 1) {
    for (var c = 0; c < code[r].length; c += 1) {
        if (code[r][c] === 1) {
            /*1% more size to cover the border of rect. */
            doc.rect(PADDING + xpos + r * R, PADDING + ypos + c * R, R * 1.01, R * 1.01, 'F');
        }
    }
}
~~~

You can test the lib [here](http://siciarek.pl/qrcode/).

