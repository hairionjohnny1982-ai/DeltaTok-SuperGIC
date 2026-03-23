
# DeltaTok SuperGIC 🇫🇷

## Novel tokenizer beating tiktoken on French, English and Code

**Author** : Aque
**Contact** : aquej@hotmail.com 

---

## What is GIC ?

GIC (Gain d'Information Conditionnel) is a novel 
tokenization algorithm that replaces BPE frequency score
with conditional entropy reduction.

BPE : score = frequency(A, B)
GIC : score = ΔH × log(len+1) × log(freq+1)

→ Merges what is most PREDICTIVE instead of most FREQUENT

---

## Benchmark vs tiktoken (cl100k)

| Text | DeltaTok | tiktoken | Ratio |
|------|----------|----------|-------|
| L'intelligence artificielle révolutionne | 7 | 13 | 0.47x ✅ |
| n'est-ce pas ? c'est-à-dire vas-tu | 5 | 14 | 0.36x ✅ |
| cardiovasculaire et neurologique | 4 | 9 | 0.44x ✅ |
| The machine learning algorithm works | 7 | 7 | 1.00x ✅ |
| for i in range(10): print(i) | 7 | 10 | 0.70x ✅ |
| SELECT * FROM users WHERE age > 18; | 9 | 10 | 0.90x ✅ |

**Global : 0.70x vs tiktoken = 30% fewer tokens**

---

## Key innovations

- Dual pre-tokenization (FR mode + Code mode)
- CODE_MARKER U+200B for code space handling  
- Byte fallback (IDs 0-255) — zero UNK guaranteed
- 64k vocab — optimal for French LLM

---

## DELTA v8 — French LLM trained with DeltaTok

246M params | 63GB French corpus | RTX 5070

**Step 4000 generation example :**

> Prompt : "Bonjour, je suis DELTA,"
> Output : "Bonjour, je suis DELTA, je suis un peu 
> différents, et je suis souvent à l'école de mon 
> futur de mon chemin de ma vie..."

---

## Contact

Interested ?  
📧 **aquej@hotmail.com**
