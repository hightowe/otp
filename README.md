# otp
Simple python program to provide Google Authenticator-style TOTP one-time passwords at the command line.

# Example usage:
    $ otp
    This script takes exactly one argument, one of these:
     * constant
     * github
     * live.com
     * login.gov
     * twilio
    Or -l to simply list all of the services...
    Or -a to print OTPs for all of the services...
    
    $ otp github
    367973
    
    $ otp -a
     constant : 240440
       github : 714866
     live.com : 866147
    login.gov : 436235
       twilio : 155662

# Installation
Install the python module onetimepass using pip:
`pip install onetimepass` or `pip3 install onetimepass`

Place the otp binary where you would like it to be and make it executable.

Copy otp.conf from this repository to the same path as the otp program or to ~/.otprc
and edit it to contain your information.

# Tab completion for bash
I find it very nice to have bash tab completion for otp and adding it is easy.
Just download bash_completion.otp and install it as per the instructions at
the top of the file.

# Encrypting your otp.conf with gpg
On October 28, 2023, support for encrypting the otp.conf was added to this repository
in the form of a wrapper script named otp-edit and updates to bash_completion.otp.
The otp-edit program assumes that you use a otp.conf that sits alongside your otp binary,
and not ~/.otprc. Please review the instructions in the comments at the top of otp-edit
to install and use this capability.

# Tips for obtaining OTP secrets
Some services/sites will display TOTP secrets that you can just copy and paste,
but many will not, choosing instead to do things such as only displaying QR codes
that are to be photographed and decoded by mobile apps such as Google Authenticator.
Those QR codes are usually encoded in a URL format like this
`otpauth://totp/Twitter?secret=<the_secret>&issuer=Twitter`. You can use a QR code
decoding app, perhaps on your mobile phone, to read those URLs. What you are interested
in is `<the_secret>` part from the `secret=<the_secret>` part of the URL.

A tool such as `zbarimg` can be used to get the URL out of a QR Code image. This page
demonstrates that: https://sts10.github.io/2018/11/26/totp-uris-qr-codes-2-factor.html
