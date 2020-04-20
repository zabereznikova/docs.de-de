---
ms.openlocfilehash: b5b724afefcce69df706f2bea0b1612db653af03
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "81274798"
---
### <a name="minimum-size-for-rsaopenssl-key-generation-has-increased"></a>Die Mindestgröße für die Generierung von RSAOpenSsl-Schlüsseln wurde heraufgesetzt

Die Mindestgröße für das Erstellen neuer RSA-Schlüssel unter Linux wurde von 384 Bit auf 512 Bit heraufgesetzt.

#### <a name="change-description"></a>Änderungsbeschreibung

Mit .NET Core 3.0 wurde die mindestens erforderliche Schlüsselgröße, die von der `LegalKeySizes`-Eigenschaft auf RSA-Instanzen von <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>, <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor%2A> und <xref:System.Security.Cryptography.RSACryptoServiceProvider.%23ctor%2A> unter Linux gemeldet wird, von 384 auf 512 erhöht.

Infolgedessen ist in . NET Core 2.2 und früheren Versionen ein Methodenaufruf wie `RSA.Create(384)` erfolgreich. In .NET Core 3.0 und höheren Versionen löst der Methodenaufruf `RSA.Create(384)` eine Ausnahme aus, die anzeigt, dass die Größe zu klein ist.

Diese Änderung wurde vorgenommen, weil für OpenSSL (Software zum Durchführen der kryptografischen Vorgänge unter Linux) der Mindestwert von Version 1.0.2 zu Version 1.1.0 erhöht wurde. .NET Core 3.0 zieht OpenSSL 1.1.x 1.0.x vor, und die mindestens gemeldete Version wurde erhöht, um dieser neuen höheren Abhängigkeitseinschränkung Rechnung zu tragen.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="recommended-action"></a>Empfohlene Aktion

Wenn Sie eine der betroffenen APIs aufzurufen, stellen Sie sicher, dass die Größe der generierten Schlüssel nicht kleiner ist als der Anbietermindestwert.

> [!NOTE]
> 384-Bit-RSA wird bereits als unsicher angesehen (ebenso wie 512-Bit-RSA). Moderne Empfehlungen (z.B. [NIST Special Publication 800-57 Part 1 Revision 4](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf)) schlagen 2048-Bit als Mindestgröße für neu generierte Schlüssel vor.

#### <a name="category"></a>Kategorie

Kryptografie

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Security.Cryptography.AsymmetricAlgorithm.LegalKeySizes?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor%2A>
- <xref:System.Security.Cryptography.RSACryptoServiceProvider.%23ctor%2A>

<!--
### Affected APIs

- `P:System.Security.Cryptography.AsymmetricAlgorithm.LegalKeySizes`
- `Overload:System.Security.Cryptography.RSA.Create`
- `Overload:System.Security.Cryptography.RSAOpenSsl.#ctor`
- `Overload:System.Security.Cryptography.RSACryptoServiceProvider.#ctor`

-->
