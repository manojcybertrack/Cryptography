# Cryptography

# Substitution Ciphers

_Substitution ciphers_ क्रिप्टोग्राफी के सबसे पुराने और आसान तरीकों में से एक हैं, जहाँ हर अक्षर या प्रतीक को किसी दूसरे अक्षर या प्रतीक से बदला जाता है।

---

## Types of Substitution Ciphers

### 1. Monoalphabetic Cipher
- पूरे मैसेज में अक्षर एक ही नियम से बदलते हैं।  
- उदाहरण: **Caesar Cipher** जहाँ हर अक्षर को एक निश्चित संख्या से शिफ्ट किया जाता है।  
- कमजोरियाँ: फ़्रीक्वेंसी एनालिसिस से आसानी से तोड़ा जा सकता है।

### 2. Polyalphabetic Cipher
- अक्षर बदलने के लिए कई अल्फाबेट्स का उपयोग होता है।  
- उदाहरण: **Vigenère Cipher**  
- अधिक सुरक्षित, क्योंकि एक ही अक्षर कई बार अलग-अलग तरीके से बदला जा सकता है।

### 3. Homophonic Substitution
- एक अक्षर के लिए कई संभावित बदल (साइफर अक्षर) हो सकते हैं।  
- फ़्रीक्वेंसी पैटर्न को छुपाता है।

### 4. Polygraphic Substitution
- अक्षरों के समूह (जैसे 2 अक्षर) को एक साथ बदलता है।  
- उदाहरण: **Playfair Cipher**

---

## Important Concepts

- **Key (कुंजी):** Substitution cipher में कुंजी तय करती है कि अक्षर कैसे बदले जाएं।  
- **Frequency Analysis:** एक तकनीक जिससे साइफर को तोड़ा जा सकता है।  
- Classical substitution ciphers अब आधुनिक क्रिप्टोग्राफी में सुरक्षित नहीं माने जाते।

---

## Example: Caesar Cipher (Monoalphabetic)

```python
def caesar_encrypt(text, shift):
    result = ""
    for char in text:
        if char.isalpha():
            offset = 65 if char.isupper() else 97
            result += chr((ord(char) - offset + shift) % 26 + offset)
        else:
            result += char
    return result

text = "Manoj Learning Cryptography"
shift = 3
encrypted = caesar_encrypt(text, shift)
print("Encrypted:", encrypted)
