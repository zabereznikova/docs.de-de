---
ms.openlocfilehash: a4476fbff572c004632153e5a98812c241efca57
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032123"
---
### <a name="openssl-versions-on-macos"></a>OpenSSL-Versionen unter macOS

Die Runtimes von .NET Core 3.0 und höher unter macOS bevorzugen jetzt OpenSSL 1.1.x-Versionen gegenüber OpenSSL 1.0.x-Versionen für die Typen <xref:System.Security.Cryptography.AesCcm>, <xref:System.Security.Cryptography.AesGcm>, <xref:System.Security.Cryptography.DSAOpenSsl>, <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>, <xref:System.Security.Cryptography.ECDsaOpenSsl>, <xref:System.Security.Cryptography.RSAOpenSsl> und <xref:System.Security.Cryptography.SafeEvpPKeyHandle>.

Die .NET Core 2.1-Runtime unterstützt jetzt OpenSSL 1.1.x-Versionen, bevorzugt aber immer noch OpenSSL 1.0.x-Versionen.

#### <a name="change-description"></a>Änderungsbeschreibung

Zuvor verwendete die .NET Core-Runtime OpenSSL 1.0.x-Versionen unter macOS für Typen, die mit OpenSSL interagieren. Die neueste Version von OpenSSL 1.0.x, OpenSSL 1.0.2, wird jetzt nicht mehr unterstützt. Um Typen, die OpenSSL auf unterstützten Versionen von OpenSSL verwenden, beizubehalten, verwenden die .NET Core 3.0 und spätere Runtimes jetzt neuere Versionen von OpenSSL unter macOS.

Mit dieser Änderung sieht das Verhalten für die .NET Core-Runtimes unter macOS wie folgt aus:

- Die Runtimes von .NET Core 3.0 und höheren Versionen verwenden OpenSSL 1.1.x, falls verfügbar, und greifen nur dann auf OpenSSL 1.0.x zurück, wenn keine 1.1.x-Version verfügbar ist.

  Für Aufrufer, die die OpenSSL-Interop-Typen mit benutzerdefinierten P/Invokes verwenden, befolgen Sie die Anleitung in den <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType>-Anweisungen. Ihre App stürzt möglicherweise ab, wenn Sie den <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion>-Wert nicht überprüfen.

- Die Runtime von .NET Core 2.1 verwendet OpenSSL 1.0.x, falls verfügbar, und greift auf OpenSSL 1.1.x zurück, wenn keine 1.0.x-Version verfügbar ist.

  Die 2.1-Runtime bevorzugt die frühere Version von OpenSSL, da die <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType>-Eigenschaft in .NET Core 2.1 nicht existiert, sodass die OpenSSL-Version zur Laufzeit nicht zuverlässig ermittelt werden kann.

#### <a name="version-introduced"></a>Eingeführt in Version

- .NET Core 2.1.16
- .NET Core 3.0.3
- .NET Core 3.1.2

#### <a name="recommended-action"></a>Empfohlene Aktion

- Deinstallieren Sie OpenSSL, Version 1.0.2, wenn es nicht mehr benötigt wird.

- Installieren Sie OpenSSL 1.1.x, wenn Sie die Typen <xref:System.Security.Cryptography.AesCcm>, <xref:System.Security.Cryptography.AesGcm>, <xref:System.Security.Cryptography.DSAOpenSsl>, <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>, <xref:System.Security.Cryptography.ECDsaOpenSsl>, <xref:System.Security.Cryptography.RSAOpenSsl> oder <xref:System.Security.Cryptography.SafeEvpPKeyHandle> verwenden.

- Wenn Sie die OpenSSL-Interop-Typen mit benutzerdefinierten P/Invokes verwenden, befolgen Sie die Anleitung in den <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType>-Anweisungen.

#### <a name="category"></a>Kategorie

Core .NET-Bibliotheken

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Security.Cryptography.AesCcm?displayProperty=fullName>
- <xref:System.Security.Cryptography.AesGcm?displayProperty=fullName>
- <xref:System.Security.Cryptography.DSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDsaOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.RSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.SafeEvpPKeyHandle?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Security.Cryptography.AesCcm``
- `T:System.Security.Cryptography.AesGcm`
- `T:System.Security.Cryptography.DSAOpenSsl`
- `T:System.Security.Cryptography.ECDiffieHellmanOpenSsl`
- `T:System.Security.Cryptography.ECDsaOpenSsl`
- `T:System.Security.Cryptography.RSAOpenSsl`
- `T:System.Security.Cryptography.SafeEvpPKeyHandle`

-->
