# Security Basics

## Concepts to learn

- **CIA triad:** Confidentiality limits disclosure; integrity prevents improper alteration; availability keeps services/data accessible.
- **Authentication and authorization:** Authentication verifies identity; authorization decides what an authenticated identity may do.
- **Least privilege:** Give each user/service only the access required for its task, and remove access when it is no longer needed.
- **MFA:** Uses at least two different factor categories (something known, possessed, or inherent); two passwords alone are not two independent factors.
- **Encryption:** Converts readable data to ciphertext using keys. Symmetric cryptography uses a shared secret key; asymmetric cryptography uses a public/private key pair.
- **Hashing:** One-way digest used for integrity checks and password verification when combined with appropriate password-hashing methods and salts; it is not encryption.
- **Phishing and social engineering:** Attempts to trick people into revealing secrets, transferring money, or opening malicious content. Verify unusual requests through a trusted channel.
- **Malware and ransomware:** Malicious software; ransomware commonly blocks/encrypts access and demands payment. Maintain protected backups and report incidents.
- **Patching and secure configuration:** Updates fix known vulnerabilities; default passwords and unnecessary services increase risk.
- **Backups and incident response:** Keep tested, access-controlled backups. Report suspected incidents promptly and preserve evidence instead of hiding or casually deleting it.

## Original practice MCQs

### Questions

1. Which CIA property concerns preventing unauthorized disclosure?
   A) Availability  B) Confidentiality  C) Integrity  D) Scalability

2. Checking a user's identity with a password is:
   A) Authorization  B) Authentication  C) Replication  D) Hash collision

3. After a user signs in, deciding whether they may read a particular file is:
   A) Authorization  B) Authentication  C) Compression  D) Address resolution

4. Which is a valid example of two-factor authentication?
   A) Password plus a second password
   B) Password plus a one-time code from a registered authenticator
   C) Username plus email address
   D) Two security questions

5. Which statement best distinguishes hashing from encryption?
   A) Hashing is designed to be one-way; encryption is designed to be reversible with a key.
   B) Hashing always uses two keys.
   C) Encryption cannot protect data.
   D) They are identical.

6. You receive an unexpected message asking you to sign in using a link and act urgently. What is the safest first step?
   A) Open the link quickly
   B) Verify the request through a known, trusted channel and report it
   C) Forward it to everyone
   D) Reply with your password

7. What does least privilege mean?
   A) Everyone gets administrator access
   B) Access is limited to what is necessary for the task
   C) Accounts never expire
   D) Passwords are shared by a team

8. Which practice best improves ransomware recovery readiness?
   A) Keep tested, protected backups separated from ordinary user write access
   B) Use the same password everywhere
   C) Disable all updates
   D) Store the only backup on the same writable device

### Answer key and explanations

1. **B — Confidentiality.** It concerns limiting information exposure.
2. **B — Authentication.** Authentication verifies who the user is.
3. **A — Authorization.** Authorization determines permitted actions.
4. **B.** A password is a knowledge factor; an authenticator code is a separate possession-based factor.
5. **A.** Encryption is reversible by an authorized key holder; a cryptographic hash is intended as a one-way digest.
6. **B.** Independently verify and use the organization's reporting procedure; don't trust an unexpected link.
7. **B.** Minimum necessary access reduces the impact of mistakes or compromised accounts.
8. **A.** Protected and tested backups support restoration and reduce the chance that malware can destroy every copy.
