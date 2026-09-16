# HeHe Android SDK — public release artifacts (AAR only)

Private sources:
- `android-sdk` — core SDK
- `android-sdk-adapter` — mediation adapters

This repository is the **public** JitPack distribution channel. It contains release AARs only — no SDK source.

## Setup

```kotlin
dependencyResolutionManagement {
    repositories {
        google()
        mavenCentral()
        maven { url = uri("https://jitpack.io") }
        // TopOn adapter only:
        // maven { url = uri("https://jfrog.anythinktech.com/artifactory/overseas_sdk") }
    }
}
```

## Dependencies

Replace `VERSION` with a git tag (e.g. `0.2.3`).

```kotlin
// Core SDK (required)
implementation("com.github.hehesdk.android-release:hehesdk:VERSION")

// Adapters — pick what you need (do NOT depend on the repo root artifact)
implementation("com.github.hehesdk.android-release:adapter-admob-nextgen:VERSION")
implementation("com.github.hehesdk.android-release:adapter-admob-legacy:VERSION")
implementation("com.github.hehesdk.android-release:adapter-max:VERSION")
implementation("com.github.hehesdk.android-release:adapter-topon:VERSION")
implementation("com.github.hehesdk.android-release:adapter-tradplus:VERSION")
```

## Host app notes

| Artifact | Host must also provide |
|----------|------------------------|
| `hehesdk` | `androidx.media3:media3-exoplayer` (and usual AndroidX) |
| `adapter-admob-nextgen` | Google Mobile Ads NextGen SDK |
| `adapter-admob-legacy` | `com.google.android.gms:play-services-ads` |
| `adapter-max` | AppLovin MAX SDK |
| `adapter-topon` | ThinkUp / TopOn `core-tpn` |
| `adapter-tradplus` | TradPlus SDK |

Adapters are thin: they do **not** bundle HeHe SDK or mediation SDKs.


