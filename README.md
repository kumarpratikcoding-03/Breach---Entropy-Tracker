\# PassAudit-Zero



> An advanced Python cybersecurity CLI tool for password auditing, breach intelligence, entropy analysis, and password crack-time estimation.



\## Project Overview



PassAudit-Zero is a security-focused command-line application that helps users evaluate the strength and security of their passwords without transmitting the password itself to third-party services.



The tool combines password entropy analysis, common weakness detection, breach exposure verification via the Have I Been Pwned (HIBP) k-anonymity model, and realistic password-cracking estimates to provide a comprehensive security assessment.



Built with Python and powered by the Rich library, PassAudit-Zero delivers professional, color-coded terminal reports suitable for learning, security awareness, and portfolio demonstration purposes.



\---



\## Security Features



\### 1. HIBP Breach Detection (k-Anonymity)



PassAudit-Zero checks passwords against the Have I Been Pwned password database using the privacy-preserving k-anonymity model.



\*\*How it works:\*\*



\- Password is hashed locally using SHA-1

\- Only the first \*\*5 uppercase SHA-1 hash characters\*\* are sent to the HIBP API

\- The remaining hash comparison occurs locally

\- Supports the `Add-Padding: true` header to reduce response-size fingerprinting

\- Plaintext passwords never leave the device



Example:



```text

Password

&#x20;  ↓

SHA-1 Hash

&#x20;  ↓

ABCDE123456789...

&#x20;  ↓

Send only: ABCDE

```



\---



\### 2. Shannon Entropy Analysis



The tool calculates password entropy using Shannon entropy principles.



Entropy analysis helps estimate how unpredictable a password is by considering:



\- Character frequency distribution

\- Character diversity

\- Password complexity



Higher entropy generally indicates stronger resistance against guessing and cracking attacks.



\---



\### 3. Pattern \& Weakness Detection



PassAudit-Zero identifies common password weaknesses including:



\#### Keyboard Walks



Examples:



```text

qwerty

asdf

zxcv

1234

```



\#### Sequential Patterns



Examples:



```text

12345

67890

abcdef

bcdefg

```



\#### Repeated Characters



Examples:



```text

aaaaaa

111111

$$$$$$

```



\#### Common Password Fragments



Examples:



```text

password

admin

letmein

welcome

```



These patterns significantly reduce real-world password strength and are flagged within the report.



\---



\### 4. Crack-Time Estimation



The tool estimates the theoretical time required to crack a password under two attack scenarios.



\#### Offline GPU Attack



Simulates a high-performance attacker using modern GPU hardware capable of billions of guesses per second.



Example:



```text

350+ billion guesses/second

```



\#### Online Rate-Limited Attack



Simulates attacks against a live authentication service with rate limits.



Example:



```text

5 guesses/second

```



Comparing both scenarios helps demonstrate the security impact of password complexity under different threat models.



\---



\### 5. Rich Terminal Reporting



PassAudit-Zero uses the Python \*\*Rich\*\* library to produce:



\- Color-coded security ratings

\- Organized assessment tables

\- Security verdict panels

\- Breach status indicators

\- Readable CLI output



Example ratings:



```text

Excellent

Strong

Moderate

Weak

```



\---



\## Installation



\### Clone the Repository



```bash

git clone https://github.com/your-username/PassAudit-Zero.git

cd PassAudit-Zero

```



\### Install Dependencies



```bash

pip install -r requirements.txt

```



Example `requirements.txt`:



```text

requests

rich

```



\---



\## Usage



Run the password auditor from the terminal:



```bash

python checker.py

```



You will be prompted to enter a password securely using hidden input:



```text

Enter password to audit:

```



The tool will then generate a complete security assessment report including:



\- Password length

\- Shannon entropy score

\- Pattern analysis

\- HIBP breach status

\- Offline GPU crack-time estimate

\- Online attack estimate

\- Overall security score

\- Security recommendation



\---



\## Example Output



```text

PassAudit-Zero

Advanced Password Security Analysis



Length:                    16

Entropy:                   72.8 bits

Security Score:            89/100

Rating:                    Excellent

HIBP Status:               Not Found



Offline GPU Crack Estimate:

1,200 years



Online Attack Estimate:

84 billion years



Security Verdict:

Password appears highly resilient.

```



\---



\## Privacy \& Security



PassAudit-Zero is designed with privacy in mind.



✅ Password hidden during entry using `getpass`



✅ Password never transmitted in plaintext



✅ Local SHA-1 hashing



✅ HIBP k-anonymity implementation



✅ Uses request padding to enhance privacy



✅ No password storage or logging



\---



\## Technologies Used



\- Python 3

\- Requests

\- Rich

\- SHA-1 Hashing

\- Have I Been Pwned API

\- Shannon Entropy Analysis



\---



\## Educational Disclaimer



PassAudit-Zero is intended for educational, defensive security, and password-awareness purposes. Crack-time estimates are theoretical approximations and should not be interpreted as guarantees of real-world resistance against all attack methods.



\---



\## License



MIT License



\---



\*\*PassAudit-Zero\*\* combines password intelligence, breach detection, entropy analytics, and security reporting into a professional cybersecurity CLI project suitable for portfolios, resume showcases, and security engineering demonstrations.

