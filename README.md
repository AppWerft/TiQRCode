TiQRCode
========

This is a titaniumified version of [Jacek Siciarek's QR code generator](https://github.com/siciarek/javascript-qrcode).  This module returns only the data matrix und this matrix you can use in rendering programms.


Usage
-----


Example for usage inside jspdf:
~~~
var PADDING = 5;
var qrcode = new (require('de.appwerfrt.qrcode'))('http://google.com','M');
var code = qrcode.getData();
var R = width / qrcode.getSize();
doc.setDrawColor(color);
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

