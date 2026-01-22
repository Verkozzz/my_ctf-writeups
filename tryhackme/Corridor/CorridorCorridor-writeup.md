# 🚪 TryHackMe — Corridor

**Difficulty:** Easy  
**Category:** Logic / Web  
**Platform:** TryHackMe

---

## 1. Description

Corridor is a logic-based challenge focused on pattern recognition and  
navigation logic rather than technical exploitation.

The task is not about breaking the system, but about understanding how  
the navigation structure is generated.

---

## 2. Enumeration

I started by navigating through the doors and analyzing the URL  
structure instead of clicking randomly.

I noticed that each door URL consisted of a 32-character hexadecimal  
string, which strongly resembled an MD5 hash.

Example: 8f14e45fceea167a5a36dedd4bea2543


This format and length suggested the use of MD5.

---

## 3. Pattern Identification

After extracting several door URLs, I compared them with MD5 hashes of  
numbers.

Examples:

- md5("1") = c4ca4238a0b923820dcc509a6f75849b  
- md5("7") = 8f14e45fceea167a5a36dedd4bea2543  

The interface presents doors numbered from 1 to 13, suggesting a finite  
navigation path.


---

## 4. Reasoning Process

After identifying the numeric pattern, I assumed that the logical next  
step would be to access the next number in the sequence.

I generated: md5("14")


and attempted to access the corresponding URL.

This did not lead to any result, which indicated that the sequence was  
not meant to be extended forward.

At this point, I reconsidered the numeric domain and asked a different  
question:

If doors exist for 1–13, which logical value is missing in the numeric  
set?

The answer is: 0


---

## 5. Exploitation

I generated: 
and accessed the corresponding URL directly.

This led to the final page and the flag.

---

## 6. Flag

Flag obtained successfully.

---

## 7. What I learned

- How deterministic URL generation creates predictable structures  
- Why validating logical domains is as important as validating input  








