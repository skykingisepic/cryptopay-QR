# cryptopay-QR
php server side app to generate QRcode for Mobile Wallet Payments

Library files downloaded from https://sourceforge.net/projects/phpqrcode/

The PHP QR Code library files are open source (LGPL) for generating QR Code, 2-dimensional barcode. Based on libqrencode C library, provides API for creating QR Code barcode images (PNG, JPEG thanks to GD2). Implemented purely in PHP.

A Payment Processing System framework. This will allow merchants (or anyone requiring a payment in Crypto) to generate a formatted QRcode that contains their receive address, invoice or memo, and amount delimited by '*' in a text string.

Crypto wallets should create a 'Pay' option where the app will scan the generated QRcode and parse the address, invoice, and amount then auto-fill these fields on the Send page to complete the transaction. The invoice/memo will be stored in the wallet's memo field (if available) for historical reference. Also helpful to append the calculated current fiat currency value of the Crypto used in the transaction to the memo invoice giving the user an historical reference to the amount in fiat needed to compute any capital gains tax (for the US or any other taxing authorities).

<b>Using cryptopayqr for Payment QRcodes:</b>

You use a browser to access the cryptopay QRcode generator. It is configured to accept the following URL formats:

https://cryptopay.domain - allows manual entry of receive address, invoice/memo, and amount. These values will reset after you generate the QRcode.

https://cryptopay.domain?receive_address - use this form of URL with a query string and it will make your receive address persistent between code generations. This is good for merchants to have running on a spare phone or tablet at checkout so all they have to do between transactions is update the invoice and amount without re-entering the receive address.

https://cryptopay.domain?receive_address*inv/memo*amount - this will populate all data fields from the URL delimited with '*' and all will be persistent. To reset, just use https://cryptopay.domain.

Note: The amount field should bring up the Numeric Keypad on mobiles.

# Installation:

clone repo and unzip the libfiles in the folder (Creates phpqrcode and vendor folders required to run cryptoqr.php)

# Deployment:

Copy cryptopayqr.php, your icon file (if used), and the two folders (vendor and phpqrcode) to a new /var/www/cryptoqr folder on your web server. Set up a virtual server and set SSL if desired, and create a DNS 'A Record' pointing to cryptoqr.yourdomain for public access. You can also run 'sudo php -S 0.0.0.0:80 -t /path-to-repofolder' from the cloned repo folder for testing locally referencing http://localhost/cryptopayqr.php from any local browser.



