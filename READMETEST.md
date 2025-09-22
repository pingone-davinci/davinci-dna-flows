# Configuration Guide

This document explains how to configure your **`gv-VariableObject`** in **PingOne DaVinci**.  
The object centralizes settings for **PingOne Protect**, **PingID**, and **PingOne Verify**.  

---

## Quick Start

Copy this template into your DaVinci **`gv-VariableObject`** and replace the placeholder values with IDs and settings from your environment.

```json
{
  "general": {
  },
  "PingOneProtect": {
    "ProtectPolicyIds": {
      "authPolicy": "YOUR_AUTH_POLICY_ID_HERE",
      "ssprPolicy": "YOUR_SSPR_POLICY_ID_HERE"
    }
  },
  "PingMFA": {
    "mandatoryAuthenticationMethods": [
      "FIDO2",
      "PINGID_MOBILE"
    ],
    "pingIdFooterMessage": "YOUR_CUSTOM_FOOTER_MESSAGE",
    "byPassMFADate": "YYYY-MM-DD",
    "allowOTPFallback": true,
    "allowedBackUpMethods": [
      "SMS",
      "EMAIL",
      "VOICE"
    ],
    "aggregateFido": false
  },
  "PingOneVerify": {
    "VerifyPolicyIds": {
      "authPolicy": "YOUR_VERIFY_POLICY_ID_HERE"
    }
  }
}

---

## Configuration

Update your **`gv-VariableObject`** Company Variable in DaVinci to represent the values from your environment.

### Variable Reference

| Variable                           | Description                                                                                             | Example Value                                                                                   |
| ---------------------------------- | ------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| `general`                          | Reserved for global settings (currently unused).                                                        | `"general": {"sample": "value"}`                                                                |
| `PingOneProtect`                   | Configuration for PingOne Protect.                                                                      | `"PingOneProtect": {}`                                                                          |
| &nbsp;&nbsp;`ProtectPolicyIds`     | Group of policy IDs for PingOne Protect.                                                                | `"ProtectPolicyIds": {}`                                                                        |
| &nbsp;&nbsp;&nbsp;&nbsp;`authPolicy` | Policy ID used for authentication flows.                                                                | `"authPolicy": "a1b23cde-f456-7890-gh12-34ij567k89lm"`                                          |
| &nbsp;&nbsp;&nbsp;&nbsp;`ssprPolicy` | Policy ID used for self-service password reset (SSPR).                                                   | `"ssprPolicy": "998e7fc1-ab8e-4d8a-bc24-117x7d66yy49"`                                          |
| `PingMFA`                          | Configuration for Multi-Factor Authentication (MFA).                                                    | `"PingMFA": {}`                                                                                 |
| &nbsp;&nbsp;`mandatoryAuthenticationMethods` | List of MFA methods required for authentication.                                                         | `"mandatoryAuthenticationMethods": ["FIDO2", "PINGID_MOBILE"]`                                  |
| &nbsp;&nbsp;`pingIdFooterMessage`  | Footer message displayed in PingID MFA prompts.                                                          | `"pingIdFooterMessage": "Copyright © 2003-2025 Ping Identity Corporation. All rights reserved."` |
| &nbsp;&nbsp;`byPassMFADate`        | Date (`YYYY-MM-DD`) after which MFA bypass is no longer allowed.                                          | `"byPassMFADate": "2026-10-15"`                                                                 |
| &nbsp;&nbsp;`allowOTPFallback`     | Boolean flag (`true`/`false`) that allows OTP fallback if primary MFA fails.                             | `"allowOTPFallback": true`                                                                      |
| &nbsp;&nbsp;`allowedBackUpMethods` | Backup MFA methods available if primary MFA is unavailable.                                              | `"allowedBackUpMethods": ["SMS", "EMAIL", "VOICE"]`                                             |
| &nbsp;&nbsp;`aggregateFido`        | Whether multiple FIDO2 authenticators are aggregated (`true`) or treated separately (`false`).            | `"aggregateFido": false`                                                                        |
| `PingOneVerify`                    | Configuration for PingOne Verify.                                                                       | `"PingOneVerify": {}`                                                                           |
| &nbsp;&nbsp;`VerifyPolicyIds`      | Group of policy IDs for PingOne Verify.                                                                  | `"VerifyPolicyIds": {}`                                                                         |
| &nbsp;&nbsp;&nbsp;&nbsp;`authPolicy` | Policy ID used for identity verification during authentication.                                          | `"authPolicy": "7eaf0d51-b7c6-4cde-9359-f5cb959de6zz"`                                          |

---

Below is an example of an **`gv-VariableObject`** Value
```json
{
  "general": {
    "sample": "value"
  },
  "PingOneProtect": {
    "ProtectPolicyIds": {
      "authPolicy": "a1b23cde-f456-7890-gh12-34ij567k89lm",
      "ssprPolicy": "998e7fc1-ab8e-4d8a-bc24-117x7d66yy49"
    }
  },
  "PingMFA": {
    "mandatoryAuthenticationMethods": [
      "FIDO2",
      "PINGID_MOBILE"
    ],
    "pingIdFooterMessage": "Copyright © 2003-2025 Ping Identity Corporation. All rights resevrd.",
    "byPassMFADate": "2026-10-15",
    "allowOTPFallback": true,
    "allowedBackUpMethods": [
      "SMS",
      "EMAIL",
      "VOICE"
    ],
    "aggregateFido": false
  },
  "PingOneVerify": {
    "VerifyPolicyIds": {
      "authPolicy": "7eaf0d51-b7c6-4cde-9359-f5cb959de6zz"
    }
  }
}
```