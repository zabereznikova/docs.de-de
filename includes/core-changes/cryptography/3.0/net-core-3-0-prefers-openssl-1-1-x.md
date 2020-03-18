---
ms.openlocfilehash: b49b2f88b130bb952b77964d5bf38374dc606385
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "74567992"
---
### <a name="net-core-30-prefers-openssl-11x-to-openssl-10x"></a>.NET Core 3.0 zieht OpenSSL 1.1.x OpenSSL 1.0.x vor

.NET Core für Linux, das über mehrere Linux-Distributionen hinweg funktioniert, kann sowohl OpenSSL 1.0.x als auch OpenSSL 1.1.x unterstützen.  .NET Core 2.1 und .NET Core 2.2 suchen zuerst nach 1.0.x und dann nach 1.1.x. .NET Core 3.0 sucht zuerst nach 1.1.x. Diese Änderung wurde vorgenommen, um Unterstützung für neue Kryptografiestandards hinzuzufügen.

Diese Änderung kann sich auf Bibliotheken oder Anwendungen auswirken, die plattformübergreifendes Interop mit den OpenSSL-spezifischen Interoptypen in .NET Core durchführen.

#### <a name="change-description"></a>Änderungsbeschreibung

In .NET Core 2.2 und früheren Versionen zieht die Runtime das Laden von OpenSSL 1.0.x dem Laden von 1.1.x vor. Dies bedeutet, dass der <xref:System.IntPtr>- und <xref:System.Runtime.InteropServices.SafeHandle>-Typ für Interop mit OpenSSL mit libcrypto.so.1.0.0/libcrypto.so.1.0/libcrypto.so.10 bevorzugt verwendet werden.

Ab .NET Core 3.0 bevorzugt die Runtime das Laden von OpenSSL 1.1.x gegenüber OpenSSL 1.0.x, sodass die Typen <xref:System.IntPtr> und <xref:System.Runtime.InteropServices.SafeHandle> für Interop mit OpenSSL mit libcrypto.so.1.1/libcrypto.so.11/libcrypto.so.1.1.0/libcrypto.so.1.1.1 verwendet werden. Infolgedessen können Bibliotheken und Anwendungen, die direkt mit OpenSSL interagieren, beim Upgrade von .NET Core 2.1 oder .NET Core 2.2 inkompatible Zeiger mit den von .NET Core bereitgestellten Werten aufweisen.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="recommended-action"></a>Empfohlene Aktion

Bibliotheken und Anwendungen, die direkte Vorgänge mit OpenSSL ausführen, müssen darauf achten, dass sichergestellt wird, dass sie die gleiche OpenSSL-Version wie die .NET Core-Runtime verwenden.

Alle Bibliotheken oder Anwendungen, die <xref:System.IntPtr>- oder <xref:System.Runtime.InteropServices.SafeHandle>-Werte aus den kryptographischen .NET Core-Typen direkt mit OpenSSL verwenden, sollten die Version der von ihnen verwendeten Bibliothek mit der neuen <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType>-Eigenschaft vergleichen, um sicherzustellen, dass die Zeiger kompatibel sind.

#### <a name="category"></a>Kategorie

Kryptografie

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Security.Cryptography.SafeEvpPKeyHandle.%23ctor%2A?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor(System.IntPtr)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSAOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSAOpenSsl.%23ctor(System.IntPtr)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSAOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSAOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDsaOpenSsl.%23ctor(System.IntPtr)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDsaOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDsaOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl.%23ctor(System.IntPtr)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Handle?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Security.Cryptography.SafeEvpPKeyHandle.#ctor`
- `M:System.Security.Cryptography.RSAOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.RSAOpenSsl.#ctor(System.Security.Cryptography.SafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.RSAOpenSsl.DuplicateKeyHandle`
- `M:System.Security.Cryptography.DSAOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.DSAOpenSsl.#ctor(System.Security.Cryptography.SafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.DSAOpenSsl.DuplicateKeyHandle`
- `M:System.Security.Cryptography.ECDsaOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.ECDsaOpenSsl.#ctor(System.Security.CryptographySafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.ECDsaOpenSsl.DuplicateKeyHandle`
- `M:System.Security.Cryptography.ECDiffieHellmanOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.ECDiffieHellmanOpenSsl.#ctor(System.Security.Cryptography.SafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.ECDiffieHellmanOpenSsl.DuplicateKeyHandle`
- `P:System.Security.Cryptography.X509Certificates.X509Certificate.Handle`

-->
