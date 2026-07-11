# Task 6: Create a Strong Password and Evaluate Its Strength

**Objective:** Understand what makes a password strong and test it against password strength criteria.

## Methodology

Seven passwords of increasing complexity were created and tested live on **passwordmeter.com**, a free online password strength checker. Each password was typed into the tool, which scores it using length, character variety, and pattern-recognition (flagging common/leaked passwords), then estimates crack time under three attack scenarios: online guessing, and offline attacks against a leaked database (secure vs. weakly-hashed).

## Results (from passwordmeter.com)

| Password | Rating | Bits | Tool Feedback | Guessing Online | Leaked DB (secure) | Leaked DB (fast) |
|---|---|---|---|---|---|---|
| `password` | **Very Weak** | — | One of the most commonly used passwords | instantly | instantly | instantly |
| `Password1` | **Very Weak** | — | One of the most commonly used passwords | instantly | instantly | instantly |
| `P@ssw0rd!23` | **Fair** | ~72 | 12+ chars recommended; uses all 4 character types | 78B years | 10B years | 582 years |
| `Tr0ub4dor&3` | **Fair** | ~72 | 12+ chars recommended; uses all 4 character types | 78B years | 10B years | 582 years |
| `correcthorsebatterystaple` | **Very Strong** | ~118 | Letters only, numbers/symbols would help; excellent length | >1 trillion years | >1 trillion years | >1 trillion years |
| `xJ9#mQ2!vL7$pR4^` | **Very Strong** | ~105 | Excellent length; all 4 character types; no common patterns | >1 trillion years | >1 trillion years | >1 trillion years |
| `jhhdbmg738i892t20h3f` (tool-generated) | **Very Strong** | ~103 | Excellent length; no common patterns | >1 trillion years | >1 trillion years | >1 trillion years |

**Key observation:** `password` and `Password1` are cracked *instantly* despite not being trivially short — because they're on every leaked-password wordlist, the tool flags them immediately as "commonly used" rather than relying on brute-force math. Meanwhile `P@ssw0rd!23` and `Tr0ub4dor&3`, despite looking "complex," only rate **Fair** — they're below the 12-character recommended minimum, showing that length matters more than symbol-stuffing. The three long/random passwords all hit **Very Strong** with crack times exceeding a trillion years.

## Key Takeaways / Best Practices

1. **Length beats complexity.** A long passphrase of random words (`correcthorsebatterystaple`) beats a short "complex-looking" password.
2. **Avoid dictionary words and predictable substitutions.** Swapping `o`→`0` or adding `!` at the end (`Password1!`) is a well-known pattern attackers already check for.
3. **Never reuse passwords** across sites — one leaked password compromises every account using it.
4. **Use a password manager** to generate and store long, random, unique passwords (like `xJ9#mQ2!vL7$pR4^`).
5. **Enable MFA/2FA** wherever possible — it protects the account even if the password is compromised.
6. **Longer random passphrases (4+ random words) are both strong and memorable.**

## Common Password Attacks

- **Brute-force attack:** tries every possible character combination systematically until it finds a match. Effectiveness depends purely on entropy (length × character pool) — this is what the table above estimates.
- **Dictionary attack:** tries real words, common passwords, and known-leaked-password lists first, rather than random combinations. This is why `password` and `Password1` fail instantly despite non-trivial entropy scores — they're in every wordlist.
- **Hybrid/rule-based attacks:** combine dictionary words with common mutations (capitalizing first letter, adding numbers/symbols at the end, leetspeak substitutions) — this is why `Password1` and similar patterns are weak.
- **Credential stuffing:** uses passwords leaked from one breach to try logging into other accounts (relies on password reuse, not password strength at all).

## Conclusion

Testing confirmed that password strength depends on both **length/randomness** and **unpredictability** (not being a known word or leaked password), not just "looking complicated." The two passwords that mixed cases, digits, and symbols but stayed under 12 characters (`P@ssw0rd!23`, `Tr0ub4dor&3`) only scored **Fair**, while three long passwords — one a plain 26-letter passphrase — scored **Very Strong** with crack times over a trillion years. The strongest, most practical approach is either a long randomly-generated password from a password manager, or a long passphrase of unrelated random words — combined with MFA and no password reuse.

**Key Concepts:** password strength, brute force attack, dictionary attack, authentication, best practices.
