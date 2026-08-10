# Dynamic Analysis in Mobile Security

## Disclaimer

This project was completed for educational purposes as part of the Holberton School cybersecurity curriculum.

All applications, binaries, network communications, and runtime manipulations were analyzed exclusively in authorized and controlled environments using dedicated Android emulators, virtual machines, or isolated test devices.

This repository does not publish:

* challenge flags;
* credentials;
* application secrets;
* reusable malicious payloads;
* complete exploitation scripts;
* operational instructions intended to compromise real applications or devices.

The documentation focuses on methodology, technical understanding, runtime analysis, security impact, and defensive lessons.

## Description

This project focuses on **dynamic analysis techniques applied to Android applications**.

While static analysis reveals how an application is structured, dynamic analysis makes it possible to observe and influence what the application actually does while running.

This includes monitoring and manipulating:

* Java and Kotlin method calls;
* native functions;
* runtime parameters;
* return values;
* memory contents;
* hidden application logic;
* encrypted data;
* network communications;
* client-side security controls;
* application state.

The project introduces runtime instrumentation and network interception techniques commonly used during authorized mobile application security assessments.

## Educational Context

This project is part of the `holbertonschool-mobile_Security` repository and follows the `static_analysis_in_mobile_security` project.

The previous project focused primarily on APK inspection, manifest analysis, decompilation, native libraries, and application logic without relying on execution.

This project extends that knowledge by examining application behavior at runtime.

The exercises reproduce several activities commonly performed during professional mobile security assessments, including:

* runtime instrumentation;
* function hooking;
* JNI and native-code analysis;
* runtime data extraction;
* encrypted communication analysis;
* HTTP interception;
* hidden method invocation;
* security-control assessment;
* application behavior manipulation.

The objective is to develop a structured methodology that combines static and dynamic evidence rather than relying exclusively on either approach.

## Static vs Dynamic Analysis

### Static Analysis

Static analysis examines the APK without executing it.

It can reveal:

* manifest configuration;
* permissions;
* application components;
* strings and resources;
* Java and Kotlin logic;
* Smali bytecode;
* native libraries;
* hardcoded endpoints;
* cryptographic routines.

However, some application behavior may remain hidden until runtime.

### Dynamic Analysis

Dynamic analysis observes the application during execution.

It can reveal:

* actual method parameters;
* return values;
* decrypted data;
* dynamically generated strings;
* runtime-only application state;
* native function behavior;
* hidden execution paths;
* network requests and responses;
* security checks triggered during execution.

Combining both approaches provides a more complete understanding of the application's attack surface and security posture.

## Learning Objectives

By completing this project, I developed a stronger understanding of:

* dynamic analysis in Android security;
* runtime instrumentation;
* Frida scripting and method hooking;
* Objection-assisted application inspection;
* Android Debug Bridge usage;
* Java and Kotlin runtime analysis;
* JNI and native function interception;
* Android native library behavior;
* method parameter and return-value inspection;
* hidden functionality discovery;
* runtime state manipulation;
* HTTP traffic interception;
* proxy configuration;
* encrypted data-flow analysis;
* cryptographic implementation review;
* client-side security controls;
* Android logging and debugging;
* professional security reporting.

## Project Scope

The project contains four practical mobile security assessments.

The progression covers:

1. runtime method instrumentation and application logic manipulation;
2. native function interception through JNI;
3. network traffic interception and cryptographic analysis;
4. discovery and invocation of hidden application functionality.

Each task uses an APK provided within an authorized training environment.

Challenge flags, application-specific secrets, complete scripts, and final exploitation procedures are intentionally excluded from this README.

## Tasks

### Task 0 - Android Runtime Security Analysis

The first task introduces dynamic instrumentation of an Android application.

The objective is to execute the target APK, identify interesting runtime methods, and observe or influence application behavior using instrumentation tools.

The assessment combines an initial static review with runtime analysis to understand how application-generated values are produced.

The analysis covers:

* emulator or test-device preparation;
* APK installation;
* package and process identification;
* application behavior observation;
* initial static reconnaissance;
* identification of relevant methods;
* Java method hooking;
* parameter inspection;
* return-value monitoring;
* runtime behavior modification;
* controlled automation of repeated tests.

Key areas of focus:

* Frida instrumentation;
* ADB;
* application lifecycle;
* Java runtime analysis;
* method hooking;
* argument manipulation;
* runtime logging;
* controlled automation.

Expected file:

```text
0-flag.txt
```

The target method, runtime values, instrumentation script, and recovered result are intentionally not disclosed.

---

### Task 1 - Hooking Native Functions in Android

The second task focuses on Android applications that process sensitive data inside native code.

The objective is to identify a native library, understand how the application communicates with it through JNI, and observe a relevant native function during runtime.

This demonstrates why analyzing only Java or Kotlin code may provide an incomplete view of an Android application's behavior.

The analysis includes:

* identifying loaded native libraries;
* reviewing Java native method declarations;
* understanding JNI boundaries;
* locating exported or relevant native symbols;
* observing runtime library loading;
* intercepting native function execution;
* inspecting arguments and return values;
* correlating native behavior with the Android application layer;
* monitoring relevant application logs.

Key areas of focus:

* JNI;
* Android native libraries;
* shared objects (`.so`);
* native symbol analysis;
* Frida Interceptor;
* Java-to-native data flow;
* native runtime inspection;
* Android Logcat.

Expected files:

```text
1-flag.txt
1-report.md
```

The native symbol, decrypted value, instrumentation code, and binary-specific extraction process are intentionally excluded from this README.

---

### Task 2 - Network Interception and Cryptographic Analysis

The third task focuses on communication between an Android application and a remote backend.

The application exchanges encrypted information with the server. The objective is to understand the communication flow, inspect the cryptographic implementation, and determine how sensitive information is protected during transmission.

The analysis combines static inspection of the APK with controlled network interception.

It covers:

* Android proxy configuration;
* HTTP traffic interception;
* request and response inspection;
* APK decompilation;
* identification of cryptographic functions;
* encoding and decoding analysis;
* key-management review;
* encrypted payload inspection;
* response-processing analysis;
* controlled modification of network data;
* verification of recovered plaintext.

Relevant technologies may include:

* AES;
* RSA;
* Base64;
* HTTP;
* JSON;
* application-specific encoding schemes.

Key areas of focus:

* Burp Suite;
* mitmproxy;
* Wireshark;
* network data flows;
* encryption implementation;
* key storage;
* sensitive data transmission;
* application-layer trust.

Expected files:

```text
2-flag.txt
2-report.md
```

Encryption keys, decrypted data, intercepted sensitive values, and complete challenge procedures are intentionally omitted.

---

### Task 3 - Revealing Hidden Application Functions

The final task focuses on application functionality that exists inside the APK but is not normally reachable through the user interface.

The objective is to combine reverse engineering and runtime instrumentation to identify relevant hidden methods and understand how they process protected information.

The assessment includes:

* APK decompilation;
* application structure review;
* hidden method identification;
* obfuscated code analysis;
* runtime class and method inspection;
* method hooking;
* controlled method invocation;
* parameter analysis;
* data-flow reconstruction;
* encoding or transformation analysis;
* runtime result validation.

Key areas of focus:

* hidden functionality;
* unreachable code paths;
* runtime method invocation;
* application logic exposure;
* obfuscation;
* encoding;
* Frida;
* Objection;
* GDB;
* reverse engineering.

Expected files:

```text
3-flag.txt
3-report.md
```

The hidden methods, invocation parameters, decoding process, and final result are not published in this documentation.

## Tools and Environment

The project may use the following tools.

### Dynamic Instrumentation

* Frida
* Objection
* GDB

### Android Environment

* Android Studio
* Android Emulator
* Android Debug Bridge (`adb`)
* Android Logcat

### APK Analysis

* JADX
* APKTool
* Ghidra
* IDA Pro

### Network Analysis

* Burp Suite
* mitmproxy
* Wireshark

### Scripting

* Python
* JavaScript for Frida instrumentation

Not every tool is required for every task. Tools are selected according to the application behavior and the specific analysis objective.

## Repository Structure

```text
dynamic_analysis_in_mobile_security/
├── README.md
├── 0-flag.txt
├── 1-flag.txt
├── 1-report.md
├── 2-flag.txt
├── 2-report.md
├── 3-flag.txt
└── 3-report.md
```

The analyzed APK files, temporary extraction directories, instrumentation scripts, and other working files may be stored separately in the local controlled analysis environment.

Flags and sensitive challenge findings are not reproduced in this README.

## Dynamic Mobile Analysis Workflow

### 1. Preserve the Original APK

The original sample is stored separately and kept unchanged.

A working copy is used for installation, extraction, and analysis.

### 2. Validate the APK

Before analysis, relevant metadata may be recorded:

* filename;
* package name;
* file size;
* cryptographic hash;
* application version;
* target Android version.

This provides a reproducible reference for the investigation.

### 3. Prepare an Isolated Android Environment

The application is installed only on a dedicated emulator or authorized test device.

The environment should not contain:

* personal accounts;
* production credentials;
* private documents;
* access to sensitive networks.

Snapshots or clean emulator states should be used when possible.

### 4. Establish a Static Baseline

Before runtime manipulation, the APK is inspected to identify potential analysis targets.

Relevant areas may include:

* activities;
* services;
* suspicious classes;
* native methods;
* cryptographic routines;
* network clients;
* hidden methods;
* hardcoded values.

Static findings help determine where runtime instrumentation should be applied.

### 5. Observe Normal Application Behavior

The application is first used normally to establish a behavioral baseline.

Observations may include:

* user interface flow;
* generated values;
* log messages;
* network requests;
* error conditions;
* native library loading;
* security checks.

### 6. Attach Runtime Instrumentation

Frida, Objection, or debugging tools are used to observe selected code paths.

Relevant information may include:

* function arguments;
* return values;
* object fields;
* runtime-generated values;
* loaded classes;
* native symbols;
* memory locations.

### 7. Manipulate Controlled Runtime State

When permitted by the exercise, values or method behavior may be modified to understand security assumptions in the client application.

The objective is to determine whether security-sensitive logic depends excessively on client-controlled state.

### 8. Monitor Network Activity

When the application communicates with a backend, network analysis may include:

* proxy configuration;
* HTTP request capture;
* response inspection;
* DNS activity;
* TLS behavior;
* encrypted payloads;
* application error handling.

### 9. Correlate Runtime and Static Findings

Observed runtime behavior is compared with the decompiled application code.

This makes it possible to validate:

* which methods actually execute;
* how values are generated;
* when encryption occurs;
* how native and managed code interact;
* how network data is processed.

### 10. Document Findings

Reports should clearly distinguish:

* setup and environment;
* methodology;
* confirmed observations;
* supporting evidence;
* security impact;
* limitations;
* remediation recommendations.

## Runtime Instrumentation

### Function Hooking

Function hooking allows an analyst to observe when a method executes.

Depending on the target, it may expose:

* parameters;
* return values;
* object state;
* execution frequency;
* calling context.

Hooking can be applied to Java methods or native functions.

### Parameter Inspection

Runtime parameters can reveal information that is difficult to recover statically, including:

* decrypted strings;
* generated identifiers;
* cryptographic material;
* dynamically created URLs;
* processed user input.

### Return-Value Inspection

Return values help determine how security-sensitive decisions are made.

Examples may include:

* validation results;
* generated values;
* security checks;
* decoded content.

### Runtime Behavior Modification

In an authorized assessment, changing arguments or return values can help determine whether an application relies on client-side assumptions that should instead be enforced by a trusted backend.

## Native Code Analysis

Android applications may use C or C++ libraries through JNI.

A simplified flow may look like:

```text
Java / Kotlin
      ↓
Native method declaration
      ↓
JNI boundary
      ↓
Native shared library
      ↓
Runtime result
```

Dynamic native analysis can help observe:

* exported functions;
* library loading;
* memory buffers;
* string transformations;
* cryptographic operations;
* native validation logic.

Native code should not automatically be considered more secure simply because it is more difficult to inspect.

## Network Interception

Mobile applications often communicate with remote services using HTTP or HTTPS.

A controlled interception setup may follow this model:

```text
Android application
        ↓
Configured proxy
        ↓
Burp Suite / mitmproxy
        ↓
Remote test service
```

This allows the analyst to inspect:

* request methods;
* headers;
* cookies;
* tokens;
* request bodies;
* responses;
* error handling;
* sensitive information transmitted by the application.

## Cryptographic Analysis

Encryption protects information only when implemented correctly.

Relevant review areas include:

* algorithm selection;
* encryption mode;
* key generation;
* key storage;
* initialization vectors;
* randomness;
* encoding;
* integrity protection;
* certificate validation.

The presence of AES, RSA, or another cryptographic algorithm does not automatically mean that the communication is secure.

Implementation details remain critical.

## SSL/TLS Pinning

Certificate pinning can restrict which certificates an application accepts when communicating with a remote service.

This can improve protection against certain interception scenarios, but during an authorized security assessment it may also limit visibility into application traffic.

Dynamic testing may therefore examine:

* whether pinning is implemented;
* where certificate validation occurs;
* whether security decisions are performed entirely on the client;
* whether the implementation fails securely.

Any bypass testing must remain restricted to the designated training application and controlled environment.

## Client-Side Security Controls

Mobile applications may implement controls such as:

* root detection;
* debugger detection;
* emulator detection;
* anti-tampering checks;
* code obfuscation;
* method protection;
* certificate pinning.

These protections can increase the difficulty of analysis, but they should not be treated as primary security boundaries.

Sensitive authorization decisions and access controls should ultimately be enforced by trusted backend systems.

## Security Relevance

### Offensive Security Perspective

The project develops techniques used during authorized mobile application penetration testing, including:

* runtime instrumentation;
* security-control assessment;
* Java method hooking;
* native function interception;
* hidden functionality discovery;
* network traffic analysis;
* client-side trust assessment;
* cryptographic implementation review;
* data-flow analysis.

These techniques help identify weaknesses that may not be visible through static inspection alone.

### Defensive Security Perspective

The same techniques help developers and security teams understand how an application behaves when examined by an attacker.

Defensive lessons include:

* avoid relying on client-side validation for critical security decisions;
* minimize sensitive information stored or processed on the device;
* protect cryptographic material;
* implement TLS validation correctly;
* enforce authorization on backend systems;
* reduce unnecessary hidden functionality;
* avoid sensitive application logging;
* apply defense in depth rather than relying only on anti-analysis mechanisms.

## Mobile Application Security Testing

This project reinforces several principles relevant to professional mobile application assessments.

An effective assessment should combine:

```text
Static Analysis
      +
Dynamic Analysis
      +
Network Analysis
      +
Native Code Analysis
      +
Security Architecture Review
```

Each technique provides a different perspective.

Static findings help identify potential weaknesses, while dynamic analysis confirms whether those weaknesses are reachable or security-relevant during execution.

## Skills Demonstrated

* Android dynamic analysis
* Runtime instrumentation
* Frida scripting
* Objection usage
* ADB device management
* Android Logcat analysis
* Java and Kotlin method hooking
* Runtime argument inspection
* Return-value analysis
* Native function interception
* JNI analysis
* Android shared-library analysis
* Runtime data-flow tracing
* APK decompilation
* Network proxy configuration
* HTTP traffic interception
* Burp Suite usage
* mitmproxy usage
* Wireshark analysis
* Cryptographic implementation review
* Hidden functionality discovery
* Client-side security-control assessment
* Security risk analysis
* Professional security reporting

## Reporting Approach

Tasks requiring reports are documented separately in their respective Markdown files.

A professional dynamic analysis report should generally include:

### Scope

Identification of the target application and the authorized analysis objective.

### Environment

Documentation of:

* emulator or device;
* Android version;
* analysis workstation;
* relevant tool versions;
* network configuration.

### Methodology

Explanation of the analysis techniques used without unnecessary reproduction of sensitive challenge answers.

### Observations

Clear description of runtime behavior supported by evidence.

### Security Impact

Explanation of why the identified behavior matters from a security perspective.

### Remediation

Recommended improvements based on the observed weakness.

### Limitations

Any conditions that restricted or influenced the analysis.

## Safety and Integrity Measures

The following precautions apply throughout the project:

* use a dedicated emulator or authorized test device;
* preserve the original APK;
* verify sample integrity;
* create clean snapshots where possible;
* do not use personal accounts;
* restrict access to production networks;
* configure proxies and certificates only inside the laboratory environment;
* store instrumentation scripts locally;
* use relative paths;
* avoid public analysis services;
* remove temporary sensitive artifacts after analysis;
* document the test environment for reproducibility.

## Why Local Analysis Is Required

Mobile security testing can expose:

* application source logic;
* backend endpoints;
* cryptographic material;
* internal infrastructure;
* proprietary functionality;
* unpublished vulnerabilities.

Uploading samples or findings to external analysis platforms can disclose information outside the intended assessment scope.

Local analysis provides greater control over:

* confidentiality;
* network access;
* evidence preservation;
* test configuration;
* reproducibility;
* application data.

## Limitations

Dynamic analysis provides visibility into real runtime behavior, but it does not automatically reveal every possible application path.

Behavior may depend on:

* Android version;
* device architecture;
* server responses;
* application state;
* user interaction;
* network availability;
* runtime permissions;
* environment checks;
* remote configuration;
* time-based conditions;
* specific input values.

Dynamic findings should therefore be correlated with static analysis and repeated under controlled conditions when necessary.

## Documentation Approach

This repository is designed as a professional mobile security learning portfolio.

The documentation focuses on:

* methodology;
* technical reasoning;
* evidence-based findings;
* security implications;
* defensive recommendations;
* transferable mobile security skills.

Challenge flags, sensitive runtime values, complete Frida scripts, extracted secrets, cryptographic keys, and directly reusable bypass procedures are intentionally excluded from this README.

## Project Status

In progress as part of the Holberton School cybersecurity curriculum.

## Author

Pierre-Yves
