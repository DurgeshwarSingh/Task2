# Task2
In this Writeup we are going to learn how to investigate spam/phishing emails

Lets first understand some keywords:-

Return-Path (Envelope From):
This is the real address used when the server sent the mail.
If this and From: are different, it’s suspicious.

SPF (Received-SPF):
SPF = Sender Policy Framework.
Checks if the sender’s server is allowed by the domain owner.
If fail or softfail, means server is not authorised → risky mail.

DKIM-Signature:
Like a digital signature from the sender’s domain.
If dkim=pass, then message is genuine. If fail, then it may be fake.

Think, You are the owner of this domain
domain : xyz.com
Email : iamadmin@xyz.com
SPF : Let i say that this sender email is authorized by me means SPF:true and if i say i am not owner of this and this is not authorized by me means SPF:false
DKIM : I am owner of xyz . I say dkim=pass means this email is genuine.If dkim=fail means not authorized by me.


DMARC: = SPF+DKIM
The domain owner’s policy: what to do if SPF/DKIM fails.
Common policies:
p=none → just watching (no action).
p=quarantine → suspicious mails may go to spam.
p=reject → fail mails get blocked.

MIME-Version / Content-Type:
Tells the format: plain text, HTML, or attachment.
If attachments are .exe, .elf,.js, .scr, or .bat → malware risk.

X-Headers (X-Mailer, X-Originating-IP, X-Spam-Status, etc.):
Extra info.
Can show which software sent the mail (like Outlook or Gmail), or spam filter score.

🚩 Red Flag Keywords / Things to Watch
spf=fail / softfail
dkim=fail
dmarc=fail
unknown or localhost in Received:
No Message-ID
Attachments with .exe, .bat, .js
Links with open.gif, pixel, or tracking IDs
Short links (bit.ly, t.co) → check properly before opening


🔗 Important links :

https://whatismyipaddress.com/

https://getprospect.com/email-finder/email-finder-by-domain

https://mxtoolbox.com/EmailHeaders.aspx

https://www.whois.com/whois/

https://checkphish.bolster.ai/

[![GIF](https://media2.giphy.com/media/v1.Y2lkPTc5MGI3NjExcDFkOWk5ZnM5dXdpdHJ2bGU4cThvbXkzYWViZ3FvaG5lczU1cDd5ciZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/trYVHReHjPyvzaNu4b/giphy.gif)](https://youtu.be/AhtYlafk2rY)
