# Komand — Data Protection Notice

**Last updated:** May 13, 2026

This Data Protection Notice explains how the Komand mobile application ("App"), developed by Paulius Masalskas ("Developer", "we", "us", or "our"), handles your information. Komand is designed to let you control a Claude Code runtime on your Mac from your iPhone. Most conversation and workspace activity is processed on your paired Mac, but the App Store version can also use developer-operated relay infrastructure to connect your devices.

---

## 1. Overview

Komand is a local-first remote companion for Claude Code on your Mac. In practice, this means:

- Your conversations, repository actions, and workspace interactions are primarily processed on your paired Mac.
- We do not operate user accounts or cloud databases for your chat content.
- We do not run analytics, advertising, or cross-app tracking.
- We do not sell your personal information.
- After the secure session is established, message contents sent between your iPhone and Mac are end-to-end encrypted.
- The App Store build may use a developer-operated hosted relay to help your iPhone reach your paired Mac.

## 2. Information We Collect

### 2.1 Information You Provide Through the App

- **Chat messages and prompts** — Your messages are sent from the iPhone to your paired Mac for processing by Claude Code. After the secure transport handshake is complete, the relay forwards encrypted payloads and cannot read message contents.
- **Photo attachments** — Images you attach from the camera or photo library are sent to your paired Mac over the secure channel.
- **Voice recordings** — When you use dictation, the App records a temporary audio file on your iPhone. Depending on availability, the audio is either (a) uploaded from the iPhone to OpenAI/ChatGPT for transcription, with the request authenticated using a ChatGPT token resolved from your paired Mac over the encrypted Komand channel, or (b) transcribed on-device using Apple's Speech framework. The fallback is decided per recording.
- **Repository and workspace actions** — Commands you initiate from the App, such as commit, pull, push, branch, file edits, terminal commands, or status actions, are executed on your paired Mac by Claude Code.

### 2.2 Information Collected Automatically

- **Pairing and identity keys** — The App generates cryptographic identity material used for secure pairing and trusted reconnect.
- **Relay and trusted-device metadata** — The App stores relay session data, trusted Mac identifiers, and reconnect metadata needed to restore a secure connection.
- **Subscription and purchase state** — We use Superwall and Apple to determine whether your Pro entitlement is active. This includes entitlement status, anonymous user identifiers, and related purchase metadata exposed by those services to the app.
- **Connection metadata** — If you use a hosted relay, the relay can process network and session metadata needed to route traffic, maintain trusted reconnect, and operate the service.

### 2.3 Information We Do Not Collect for Analytics or Advertising

- We do **not** collect analytics, telemetry, advertising profiles, or behavioral tracking data.
- We do **not** use third-party advertising SDKs.
- We do **not** track you across other companies' apps or websites.
- We do **not** require your name, phone number, or email address to use the App.

If you contact us directly, we will of course receive whatever information you include in that message.

## 3. How We Use Information

We use the information above only to operate and secure Komand, including:

- pairing your iPhone with your Mac
- routing encrypted traffic between your iPhone and Mac
- performing trusted reconnect
- checking and restoring subscription entitlements
- transcribing voice input when you explicitly use dictation
- maintaining app security, stability, and abuse prevention for the hosted infrastructure

We do not use your information for advertising, profiling, or resale.

### 3.1 GDPR Legal Bases

If you are in the European Economic Area or United Kingdom, we rely on the following legal bases:

- **Contract performance** — to provide the App's core features, including pairing, relay transport, voice transcription, and subscription handling
- **Legitimate interests** — to secure the service, prevent abuse, maintain relay connectivity, and protect users and infrastructure
- **Consent** — for permissions such as camera, microphone, photo library, speech recognition, and local network access

## 4. Services That Process Data

### 4.1 Developer-Operated Komand Infrastructure

The App Store build can use developer-operated infrastructure for:

- **Hosted relay transport** — to route traffic between your iPhone and paired Mac when direct connectivity is not used
- **Trusted reconnect resolution** — to help your already-paired iPhone locate the current live session for your trusted Mac

This infrastructure may process:

- session identifiers and trusted-device metadata
- connection metadata such as IP address, timestamps, and route-level request data
- secure control messages needed to establish the encrypted session

Once the secure session is active, the hosted relay does **not** decrypt your Komand application payloads.

### 4.2 Anthropic (Claude Code)

Claude Code runs on your paired Mac and communicates with Anthropic's API to generate responses. Your prompts, file contents shared with Claude Code, and tool-use results are transmitted from your Mac to Anthropic according to your Mac-side Claude Code configuration and authentication (for example, your Anthropic API key or Claude subscription).

- Anthropic privacy policy: [anthropic.com/legal/privacy](https://www.anthropic.com/legal/privacy)

The Developer does not operate or intermediate that connection — it is established directly by Claude Code on your Mac.

### 4.3 OpenAI / ChatGPT

When you use dictation and the cloud transcription path is selected, your audio recording is sent from the iPhone to OpenAI/ChatGPT for speech-to-text transcription.

- Privacy policy: [openai.com/privacy](https://openai.com/privacy)

If cloud transcription is unavailable or fails, the App falls back to Apple's on-device Speech framework and your audio is not sent to OpenAI for that recording.

### 4.4 Superwall

Superwall is used to render the in-app paywall and to coordinate paywall placements and user attributes. Superwall may process an anonymous app user identifier, entitlement-related events, paywall events, and device/app metadata.

- Privacy policy: [superwall.com/privacy](https://superwall.com/privacy)

### 4.5 Apple

Apple provides:

- App Store billing and subscription management (StoreKit)
- the Speech framework used for on-device fallback transcription
- iOS permission and platform services used by the app

- Privacy policy: [apple.com/privacy](https://www.apple.com/privacy/)

## 5. Data Storage and Security

### 5.1 On Your iPhone

- **Keychain** — sensitive values such as identity keys, pairing state, relay credentials, and encryption keys
- **Encrypted message cache** — chat history is stored locally in encrypted form using a Keychain-backed key
- **UserDefaults** — non-sensitive preferences and interface settings
- **Temporary files** — voice recordings are stored temporarily during capture/transcription

### 5.2 On Your Mac

Your paired Mac runs the local Komand bridge and the Claude Code runtime. Chat handling, repository operations, terminal commands, and workspace actions are performed there.

### 5.3 On Hosted Relay Infrastructure

When the hosted relay is used, the server side may keep limited operational state such as active session state and trusted reconnect metadata needed to route traffic and restore a secure connection.

### 5.4 In Transit

- The iPhone and Mac establish an end-to-end encrypted session using modern cryptography.
- The relay can observe connection metadata and secure-session setup traffic, but not encrypted application payloads after the secure session is established.
- Voice transcription, paywall, and subscription requests are sent over HTTPS/TLS.

## 6. Data Retention

- **Chat history on iPhone** — stored locally until the app's local storage is removed. Unpairing or forgetting a Mac does **not** automatically erase local chat history.
- **Voice recordings** — temporary voice files are deleted by the app after transcription completes or fails.
- **Pairing and trusted-device state** — retained in local app storage and Keychain until removed by app actions or platform behavior.
- **Subscription records** — retained by Apple and Superwall according to their own policies.

We do not maintain a cloud chat history database for your message contents.

## 7. Your Choices

### 7.1 Permissions

You can revoke camera, microphone, photo library, speech recognition, and local network permissions at any time in iOS Settings. Doing so disables the related feature.

### 7.2 Subscription Management

You can manage or cancel your subscription through Apple account settings or through the in-app management link when available.

### 7.3 Local Data and Reset

- Deleting the app removes ordinary app-container files such as local encrypted chat history and temporary files.
- Keychain items are managed by iOS separately from ordinary app files and may persist differently, including across reinstall scenarios.
- If you want to reset pairing/trusted-device state before deleting or reinstalling the app, use the in-app forget/unpair controls first.

## 8. Privacy Rights

Depending on your jurisdiction, you may have rights to access, correct, delete, restrict, or object to the processing of personal information, and to request portability where applicable.

Because Komand is primarily local-first, much of your data remains under your direct control on your devices. We do not maintain a centralized database of your personal data. Some data may be processed or retained by Apple, Superwall, Anthropic, and OpenAI according to their own operational needs and policies.

### 8.1 California Notice

We do not sell or share personal information for cross-context behavioral advertising.

### 8.2 Singapore (PDPA) Notice

If you are in Singapore, you may contact us to withdraw consent, request access to your personal data, or request a correction. We will respond in accordance with the Personal Data Protection Act.

## 9. Children's Privacy

The App is not directed to children under 13, or the minimum age required by local law. We do not knowingly collect personal information from children.

## 10. International Transfers

Depending on where you use the App and where service providers or hosted infrastructure are located, data processed by Apple, Superwall, Anthropic, OpenAI, or the hosted relay may be handled outside your country of residence.

## 11. Changes to This Policy

We may update this Data Protection Notice from time to time. When we do, we will update the "Last updated" date above.

## 12. Contact

If you have questions about this Data Protection Notice or want to exercise your privacy rights, you can reach us at:

- **Email:** pauliusmasalskasco@gmail.com
- **GitHub:** [github.com/PauliusOS/komand-app](https://github.com/PauliusOS/komand-app)
- **X (Twitter):** [@0xpaulius](https://x.com/0xpaulius)
