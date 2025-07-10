<p align="center">
<img src="https://i.imgur.com/aHccK9f.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Detecting Phishing Emails by Hand: A Practical Analysis</h1>
This project demonstrates the use of Network Security Groups (NSGs) in Microsoft Azure to enhance the security of virtual machines by blocking ICMP traffic. ICMP (Internet Control Message Protocol) is commonly used for network diagnostics, such as ping requests, but can also be used to cause a denial of service attack.<br />

<h2>Environments and Technologies Used</h2>

- MxToolbox
- Notepad++

<h2>Analysing the Email Header</h2>

<p>
The email header is one of the most effective ways of detecting a phishing attack. To take a look at the email header, we have to download it. In Gmail, all you have to do is click on the 3 dots and download. It downloads a file in eml format. 
</p>
<p>
<img src="https://i.imgur.com/cQRMRLp.png"/>
</p>

<br />

<p>
IN this lab, we will be taking a look at a sample from the letsdefend platform. After downloading the email, we can use Notepad++ to take a look at the information contained in the header.</p>
<p>
<img src="https://i.imgur.com/ZYcnVCY.png"/>
</p>

<br />

<p>
I know it looks all messed up, but in reality, we just want to make sure certain things are taken into consideration to determine if it is a legitimate email or not. We want to take a look at ;
</p>
<li>From or Sender Info</li>
<li>SMTP Info</li>
<li>Return path or Return to info</li>

<h2>From or Sender Information</h2>
<br />

<p>
One of the most important steps in identifying a phishing email is verifying the sender's identity. Spoofing an email address is easy. Don’t rely only on the displayed name; it is good practice to always check the actual email address and ensure it matches the legitimate domain. If the sender looks unfamiliar or suspicious, it's worth investigating further before interacting with the email</p>
<p>
<img src="https://i.imgur.com/sRGfNiP.png"/>
</p>

<h2>Return-path or Reply-To info</h2>
<br />

<p>
The Return-Path (also known as Reply-To) address should typically match the sender’s From address. If these addresses don’t match, it’s a strong indicator that the sender may be attempting to redirect your reply to a different email account, which is a common tactic used in phishing scams. Always compare these fields closely when analyzing a suspicious email.<p>
<img src="https://i.imgur.com/6swd3TT.png"/>
</p>


<h2>SMTP Information</h2>
<br />

<p>To determine if an email is legitimate, it's important to cross-check the SMTP server information found in the email header with the official MX records of the sender’s domain. This helps verify whether the email was actually sent from a server authorized by that domain.
<p>
<img src="https://i.imgur.com/8JJ4P69.png"/>
</p>

<p>To verify if an email came from a legitimate source, we can use MxToolbox to check the domain's official SMTP servers. By entering the sender's domain (e.g., daun.net) into the MX Lookup tool, we get a list of authorized mail servers for that domain. We then compare these to the SMTP IP address found in the email header — in this case, 222.227.81.181. If the IP address in the header doesn’t match any of the MX records, it’s a strong sign that the email may be spoofed and not from a trusted source.</p>
<img src="https://i.imgur.com/JckjrtX.png"/>
<br />



<h2>Thank you for reading through the project</h2>



