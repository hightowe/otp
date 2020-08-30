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
    $ otp github
    367973

# Installation
Install the python module onetimepass using pip:
`pip install onetimepass` or `pip3 install onetimepass`

Place the otp binary where you would like it to be and make it executable.

Copy otp.conf from this repository to the same path as the otp program or to ~/.otprc
and edit it to contain your information.
