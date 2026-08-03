# Static Analysis in Mobile Security

## Disclaimer

This project was completed for educational purposes as part of the Holberton School cybersecurity curriculum.

All APK files and native libraries are analyzed exclusively in authorized and controlled environments. Any runtime validation is performed on a dedicated Android emulator, virtual machine, or isolated test device.

This repository does not publish:

* challenge flags;
* application secrets;
* credentials;
* reusable exploit code;
* complete reverse engineering solutions;
* operational instructions intended to compromise real applications or devices.

The documentation focuses on analysis methodology, security concepts, technical reasoning, and defensive lessons.

## Description

This project focuses on **static analysis techniques applied to Android applications**.

An Android APK can contain several layers of information, including:

* compiled DEX bytecode;
* application resources;
* manifest configuration;
* embedded assets;
* third-party libraries;
* native shared libraries;
* network configuration;
* obfuscated application logic.

Static analysis makes it possible to inspect these components without executing the application. It helps analysts understand the application's structure, declared capabilities, internal logic, data flows, and potential security risks.

The project also introduces limited dynamic analysis techniques when runtime observation is necessary to confirm findings obtained through static inspection.

## Educational Context

This project is part of the `holbertonschool-mobile_Security` repository and the Holberton School cybersecurity specialization.

The exercises reproduce several activities commonly performed during a mobile application security assessment:

* APK extraction;
* Android manifest review;
* Java and Kotlin decompilation;
* Smali inspection;
* resource analysis;
* network communication review;
* obfuscation analysis;
* native library reverse engineering;
* Java Native Interface analysis;
* performance and algorithm analysis.

The objective is not only to recover challenge-specific values, but to develop a structured and repeatable mobile security methodology.

## Project Objectives

The project aims to develop the ability to:

* understand the internal structure of Android applications;
* inspect APK files without running them;
* identify security-relevant permissions and components;
* analyze decompiled Java, Kotlin, and Smali code;
* locate hidden or obfuscated application logic;
* inspect application resources and configuration files;
* analyze HTTP communication with backend services;
* identify insecure data-transmission practices;
* understand how Android applications use native libraries;
* follow data between Java and native code through JNI;
* reverse engineer compiled `.so` libraries;
* recognize inefficient algorithms and performance bottlenecks;
* document findings professionally without exposing sensitive answers.

## Project Scope

The project contains four practical analysis tasks.

The progression covers:

1. recovering hidden application logic through APK inspection;
2. analyzing communication between an Android application and a backend service;
3. studying computational logic and optimization opportunities;
4. reverse engineering native Android libraries and JNI interactions.

Each task uses a dedicated APK provided within the authorized training environment.

Challenge answers and binary-specific implementation details are intentionally excluded from this README.

## Tasks

### Task 0 - Android Application Security Analysis

The first task introduces the static analysis of an Android APK.

The objective is to inspect the application package, understand how its validation mechanism works, and identify hidden or obfuscated logic without executing the application.

The analysis includes:

* extracting the APK contents;
* reviewing `AndroidManifest.xml`;
* inspecting application resources;
* decompiling DEX bytecode;
* analyzing Java, Kotlin, or Smali code;
* identifying string transformations;
* locating encoded or fragmented data;
* following the application's validation flow;
* reconstructing the relevant high-level logic.

Key areas of focus:

* APK structure;
* static reconnaissance;
* application resources;
* decompilation;
* obfuscated methods;
* string manipulation;
* validation logic;
* control-flow analysis.

Expected file:

```text
0-flag.txt
```

The recovered value and application-specific validation logic are not disclosed in this documentation.

---

### Task 1 - Communication Between Device and Backend

The second task focuses on how mobile applications exchange information with backend services.

The target application processes device-related information, formats it as JSON, and sends it to a remote service through an HTTP request.

The objective is to analyze this communication flow and understand the security implications of transmitting application or device data over a network.

The analysis covers:

* identifying network-related code;
* reviewing OkHttp usage;
* understanding HTTP POST requests;
* examining JSON serialization;
* tracing device information;
* reviewing asynchronous request handling;
* analyzing response-processing logic;
* identifying error-handling mechanisms;
* reviewing application logging;
* evaluating transport-security risks.

Key areas of focus:

* client-server communication;
* HTTP request construction;
* JSON data formatting;
* asynchronous callbacks;
* backend endpoint identification;
* error handling;
* sensitive data exposure;
* insecure transport protocols;
* debugging through Android Logcat.

Expected file:

```text
1-flag.txt
```

The target endpoint, challenge result, and application-specific communication details are intentionally omitted.

---

### Task 2 - Reverse Engineering and Optimization

The third task combines reverse engineering, mathematical reasoning, and algorithm optimization.

The objective is to inspect compiled application logic, understand the mathematical operations being performed, identify inefficient computation, and determine how the implementation could be improved.

The analysis may combine static code inspection with controlled runtime observation and local scripting.

The task covers:

* reconstructing compiled program logic;
* identifying computationally expensive operations;
* understanding recursive or iterative algorithms;
* analyzing time and space complexity;
* reproducing mathematical behavior in Python;
* validating results with local scripts;
* identifying performance bottlenecks;
* applying optimization techniques;
* confirming that optimized logic preserves correctness.

Potential optimization techniques include:

* memoization;
* dynamic programming;
* reduction of repeated calculations;
* optimized matrix operations;
* improved mathematical algorithms;
* efficient data structures.

Key areas of focus:

* algorithm reconstruction;
* mathematical computation;
* Big O analysis;
* performance profiling;
* optimization;
* result validation;
* reverse engineering of application logic.

Expected file:

```text
2-flag.txt
```

The recovered algorithm, optimized implementation, and challenge-specific result are not included in this README.

---

### Task 3 - Static Analysis and Native Libraries

The final task focuses on Android applications that combine managed Java or Kotlin code with compiled native code.

Android applications may use native shared libraries to improve performance, reuse existing C or C++ code, or make reverse engineering more difficult.

The objective is to analyze both sides of the application and understand how information moves between the Android code and the native library.

The analysis includes:

* extracting the APK;
* locating native `.so` libraries;
* identifying supported processor architectures;
* decompiling the Java or Kotlin layer;
* identifying native method declarations;
* examining JNI function signatures;
* disassembling the native library;
* identifying relevant native functions;
* tracing input from Java to native code;
* reconstructing validation or transformation logic;
* identifying obfuscation techniques;
* assessing potential security weaknesses.

Key areas of focus:

* Android native libraries;
* ELF shared objects;
* JNI communication;
* Java-to-native data flow;
* native function analysis;
* ARM or x86 assembly;
* application obfuscation;
* native input validation;
* mixed static and dynamic analysis.

Expected file:

```text
3-flag.txt
```

The native validation logic, binary-specific constants, and challenge result are intentionally excluded.

## Tools and Environment

The project may use the following tools.

### APK Analysis

* JADX
* APKTool
* Dex2jar
* JD-GUI
* Android Studio

### Reverse Engineering

* Ghidra
* IDA Pro
* Radare2
* Smali and Baksmali

### Dynamic Validation

* Frida
* GDB
* Android Debug Bridge
* Android Logcat
* Android Studio Profiler

### Programming and Optimization

* Python
* NumPy
* Valgrind
* JMH

Not every tool is required for every task. Tools are selected according to the application structure and the type of analysis being performed.

## Repository Structure

```text
static_analysis_in_mobile_security/
├── README.md
├── 0-flag.txt
├── 1-flag.txt
├── 2-flag.txt
└── 3-flag.txt
```

The analyzed APK files may be stored separately within the local controlled environment.

The flag files contain the plain-text answers required for academic submission. Their contents are not reproduced in this README.

## Android APK Analysis Workflow

### 1. Preserve the Original APK

The original sample is stored separately and kept unchanged.

A working copy is used for extraction, decompilation, and analysis.

### 2. Validate File Integrity

A cryptographic hash can be calculated before analysis to:

* identify the sample;
* detect accidental modifications;
* verify that the application has not been corrupted;
* maintain reproducible findings.

### 3. Inspect the APK Structure

The APK is treated as an archive and reviewed for relevant components such as:

```text
AndroidManifest.xml
classes.dex
resources.arsc
res/
assets/
lib/
META-INF/
```

### 4. Review the Manifest

The manifest provides information about:

* package name;
* minimum and target Android versions;
* requested permissions;
* activities;
* services;
* broadcast receivers;
* content providers;
* exported components;
* intent filters;
* application configuration.

### 5. Analyze Resources

Application resources may reveal:

* strings;
* URLs;
* configuration values;
* interface elements;
* embedded files;
* certificates;
* encoded content;
* hidden development information.

### 6. Decompile Application Bytecode

DEX files are converted into readable Java-like or Kotlin-like code.

When decompilation is incomplete, Smali code can provide a lower-level representation of Android bytecode.

### 7. Identify Security-Relevant Logic

Priority is given to code related to:

* input validation;
* authentication;
* cryptography;
* network communication;
* file access;
* sensitive logging;
* native methods;
* hidden application features.

### 8. Follow Data Flow

Relevant values are traced from their source to their destination.

A simplified data flow may look like:

```text
User or device input
        ↓
Application processing
        ↓
Validation or transformation
        ↓
Local storage, native library, or network request
```

### 9. Analyze Native Libraries

When native libraries are present, the analysis includes:

* file format identification;
* architecture detection;
* imported and exported functions;
* strings;
* JNI entry points;
* disassembly;
* decompilation;
* cross-references;
* function control flow.

### 10. Confirm Findings

When static evidence is insufficient, controlled dynamic analysis may be used to observe:

* function calls;
* runtime parameters;
* memory values;
* dynamically generated strings;
* network activity;
* Java-to-native interactions.

### 11. Document the Results

Findings are organized to distinguish:

* confirmed behavior;
* likely behavior;
* supporting evidence;
* security impact;
* analysis limitations;
* recommended mitigations.

## Static Analysis Techniques

### Manifest Analysis

Manifest review helps identify the application's declared attack surface and capabilities.

Particular attention may be given to:

* sensitive permissions;
* exported components;
* debug configuration;
* backup settings;
* cleartext traffic settings;
* custom permissions;
* deep links.

### String and Resource Analysis

Strings and resources can reveal:

* API endpoints;
* hardcoded identifiers;
* application messages;
* configuration values;
* cryptographic material;
* hidden functionality.

These elements provide investigation leads but must be correlated with code usage.

### Decompilation

Decompilation converts Android bytecode into a higher-level representation.

The output is not the original source code. It may contain:

* incorrect variable names;
* missing type information;
* simplified control structures;
* decompilation errors;
* compiler-generated methods.

Important findings should therefore be confirmed through Smali or native disassembly when necessary.

### Cross-Reference Analysis

Cross-references help identify:

* where a string is used;
* which function calls a method;
* where network requests are constructed;
* how input reaches a validation function;
* where native methods are invoked.

### Obfuscation Analysis

Obfuscation may include:

* meaningless class and method names;
* encoded strings;
* fragmented constants;
* complex control flow;
* reflection;
* dynamically loaded code;
* logic moved into native libraries.

The objective is not always to fully remove the obfuscation, but to recover enough meaning to understand security-relevant behavior.

## Native Code and JNI

JNI allows Java or Kotlin code to communicate with native C or C++ libraries.

A typical interaction follows this pattern:

```text
Java or Kotlin method
        ↓
Native method declaration
        ↓
JNI function
        ↓
Compiled native logic
        ↓
Return value to the Android layer
```

Native code can increase analysis complexity because it may:

* use different processor architectures;
* lack readable symbols;
* contain optimized assembly;
* use low-level memory operations;
* hide validation or cryptographic logic;
* introduce memory-safety vulnerabilities.

Understanding both the managed and native layers is therefore important during a complete Android security assessment.

## Network Security Considerations

Mobile applications frequently exchange sensitive information with remote services.

Relevant risks include:

* unencrypted HTTP communication;
* weak certificate validation;
* hardcoded backend endpoints;
* sensitive data in request bodies;
* excessive logging;
* insufficient error handling;
* leaked device identifiers;
* insecure authentication tokens;
* missing request validation.

Recommended defensive practices include:

* enforce HTTPS;
* validate certificates correctly;
* avoid sending unnecessary device information;
* minimize sensitive logs;
* protect authentication material;
* validate backend responses;
* apply secure timeout and retry policies;
* handle failures without exposing sensitive details.

## Security Relevance

### Offensive Security Perspective

The project develops techniques useful during authorized mobile application penetration testing, including:

* application attack-surface discovery;
* hidden method identification;
* reverse engineering of validation logic;
* backend endpoint analysis;
* obfuscation review;
* native library assessment;
* Java-to-native data-flow analysis;
* identification of insecure implementation choices.

### Defensive Security Perspective

The same techniques help defenders and developers:

* identify risks before release;
* review sensitive permissions;
* detect hardcoded secrets;
* secure backend communication;
* improve application architecture;
* reduce unnecessary exposure;
* strengthen native code;
* validate security controls;
* understand how an attacker may inspect the application.

## Skills Demonstrated

* Android APK structure analysis
* Android manifest review
* Permission and component analysis
* Java and Kotlin decompilation
* Smali inspection
* Static code analysis
* Application control-flow analysis
* String and resource analysis
* Obfuscation analysis
* HTTP and JSON communication review
* OkHttp analysis
* Android Logcat usage
* Algorithm reconstruction
* Computational complexity analysis
* Performance optimization
* Native library reverse engineering
* ELF shared-library analysis
* JNI analysis
* Java-to-native data-flow tracing
* Ghidra and IDA Pro usage
* Frida-assisted runtime validation
* Mobile security risk assessment
* Professional technical documentation

## Safety and Integrity Measures

The following precautions apply throughout the project:

* use a dedicated Android emulator or isolated test device;
* avoid personal accounts and credentials;
* preserve the original APK;
* verify file hashes before analysis;
* keep regular backups of scripts and findings;
* use relative paths in scripts;
* configure monitoring tools before execution;
* restrict external network access where appropriate;
* use local tools only;
* do not upload samples to public analysis platforms;
* clearly separate confirmed findings from assumptions.

## Why Local Analysis Is Required

Using online analysis services may expose:

* proprietary applications;
* confidential samples;
* internal endpoints;
* application secrets;
* investigation details;
* unpublished vulnerabilities.

Local analysis provides greater control over:

* confidentiality;
* network access;
* evidence preservation;
* tool configuration;
* reproducibility;
* analysis scope.

## Limitations

Static analysis provides extensive information without executing the application, but some behavior may remain hidden until runtime.

Analysis may be complicated by:

* code obfuscation;
* encrypted strings;
* reflection;
* native libraries;
* dynamically loaded code;
* server-controlled behavior;
* compiler optimization;
* environment checks;
* anti-debugging mechanisms;
* emulator detection.

For these reasons, static analysis may be complemented by controlled dynamic validation when permitted by the project scope.

## Documentation Approach

This repository is designed as a professional mobile security learning portfolio.

The documentation focuses on:

* structured methodology;
* technical reasoning;
* security impact;
* tool usage;
* defensive recommendations;
* transferable mobile security skills.

Challenge flags, complete solving scripts, application secrets, vulnerable constants, and directly reusable exploitation procedures are intentionally excluded.

## Project Status

In progress as part of the Holberton School cybersecurity curriculum.

## Author

Pierre-Yves
