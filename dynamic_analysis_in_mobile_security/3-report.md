# Revealing Hidden Functions & Flag Extraction Report - Task 3

## Executive Summary
This report details the static reverse engineering process used to locate, reconstruct, and execute the hidden cryptographic function within `Apk_task3`. Using JADX code decompilation, an unreferenced method was identified, analyzed, and reimplemented in Python to recover the target secret flag without requiring active runtime execution or device emulation.

## Target Details
- **APK Name:** task3_d.apk
- **Tools Used:** JADX, Python 3
- **Target Class:** `com.holberton.task4_d.MainActivityKt`
- **Hidden Function:** `aBcDeFgHiJkLmNoPqRsTuVwXyZ123456`

## Technical Methodology

### 1. Discovery of Hidden Methods
Code inspection using JADX revealed the obfuscated method `aBcDeFgHiJkLmNoPqRsTuVwXyZ123456(Function1 setFlag)`. This function is never invoked during normal execution flows within `MainActivity`.

### 2. Analysis of the Encoding Mechanism
The hidden method performs multi-stage transformations on a hardcoded Base64 string (`8CP4zSyn...`):
1. **Base64 Decoding:** Converts the hardcoded payload into a raw byte array.
2. **XOR Transformation:** Applies `value ^ 19` to each byte.
3. **Bitwise Rotation:** Performs a 2-bit right rotation: `((temp >> 2) | (temp << 6)) & 255`.
4. **Index-Based Offset:** Subtracts `(index * 3)` modulo 256.
5. **Modular Multiplication:** Multiplies the intermediate byte by `183` modulo 256 to convert to ASCII characters.

### 3. Offline Reconstruction
To bypass the need for runtime instrumentation (Frida/Objection) on non-emulated environments, the algorithm was reimplemented in a Python script (`solve_task3.py`). The script processed the 51-byte array to sequentially recover every character of the secret message.

## Vulnerabilities Identified
1. **Hidden/Dead Code Exposure:** Unused or internal debug/flag-releasing functions left in production builds remain accessible via reverse engineering.
2. **Reversible Custom Obfuscation:** Custom mathematical transformations (XOR, rotation, linear congruent operations) do not provide effective security against static analysis.

## Remediation Recommendations
- Strip unreferenced code, debug methods, and testing endpoints prior to production release (e.g., using R8 / ProGuard rules).
- Avoid storing sensitive data or recovery routines inside client-side binaries.

## Extracted Flag
The extracted flag has been written to `3-flag.txt`.
