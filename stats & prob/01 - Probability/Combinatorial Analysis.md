---
topic: Combinatorial analysis
date: 2026-04-02
status: 🌿 growing
---

## 💡 Core Idea (ภาษาตัวเอง 1-2 ประโยค)
เหมือนเรื่องที่เรียนตอนมัธยมอะ หลักการนับ การเรียงสับเปลี่ยน การจัดหมู่ เอาไว้ใช้คำนวณทุกกรณีที่เป็นไปได้ เช่น มีรหัส 4 หลัก ตั้งแต่ 0-9 ก็จะมีรหัสที่เป็นไปทั้งหมด 10^4 วิธี เป็นต้น P ต่างกับ C ตรงที่ P สนลำดับ ส่วน C ไม่สน

## 📐 Formal Definition
**Combinatorial analysis** is formally defined as the **mathematical theory of counting**.
Its primary purpose in the study of probability is to provide effective methods for determining the number of different ways that a certain event can occur. This is particularly useful in "simple sample spaces," where all outcomes are assumed to be equally likely; in such cases, the probability of an event is simply the ratio of the number of outcomes in that event to the total number of outcomes in the sample space

## 🔗 เชื่อมกับอะไร
- [[  ]] เพราะ...

## 🐍 Python ที่เกี่ยว
```python
def factorial(number):
    if number == 0 or number == 1:
        return 1
    result = 1
    for i in range(2, number + 1):
        result *= i
    return result

def combinations(n, r):
    if r < 0 or r > n:
        return 0
    numerator = factorial(n)
    denominator = factorial(r) * factorial(n - r) 
    return numerator // denominator

def permutations(n, r):
    if r < 0 or r > n:
        return 0
    numerator = factorial(n)
    denominator = factorial(n - r)
    return numerator // denominator
```

## 📝 โจทย์ที่ลองทำ
มีพอร์ตหุ้น 12 ตัว อยากเลือกมา 4 ตัวเพื่อ short ถามว่ามีกี่วิธี?
 > 12!/4!8! = 495 วิธี

จาก portfolio 12 ตัวเดิม แบ่งเป็นหุ้นไทย 7 ตัว หุ้นต่างประเทศ 5 ตัว อยากเลือกมา 4 ตัว โดยต้องมีหุ้นไทยอย่างน้อย 2 ตัว มีกี่วิธี?
 > แบ่งเป็น 3 กรณี 
  1. หุ้นไทย 2 ตัว หุ้นนอก 2 ตัว ได้ 7 เลือก 2 คูณ 5 เลือก 2 ได้ 21 * 10 = 210 วิธี
  2. หุ้นไทย 3 ตัว หุ้นนอก 1 ตัว ได้ 7 เลือก 3 คูณ 5 เลือก 1 ได้ 35 * 5 = 175 วิธี
  3. หุ้นไทย 4 ตัว หุ้นนอก 0 ตัว ได้ 7 เลือก 4 คูณ 5 เลือก 0 ได้ 35 * 1 = 35 วิธี
 > รวมกันได้ 420 วิธี