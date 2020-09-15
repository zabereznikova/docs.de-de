---
ms.openlocfilehash: 36a9db601f7637185bf48dfcbe2233b4489fcdcf
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614442"
---
### <a name="aescryptoserviceprovider-decryptor-provides-a-reusable-transform"></a>Die AesCryptoServiceProvider-Entschlüsselungsmethode stellt eine wiederverwendbare Transformation bereit

#### <a name="details"></a>Details

Für Apps mit der Zielplattform .NET Framework 4.6.2 und höher stellt die <xref:System.Security.Cryptography.AesCryptoServiceProvider>-Entschlüsselungsmethode eine wiederverwendbare Transformation bereit. Nach einem Aufruf von <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName> wird die Transformation erneut initialisiert und kann wiederverwendet werden. Bei Apps mit früheren Versionen von .NET Framework als Zielplattform wird bei dem Versuch, die Entschlüsselungsmethode durch Aufrufen von <xref:System.Security.Cryptography.CryptoAPITransform.TransformBlock(System.Byte[],System.Int32,System.Int32,System.Byte[],System.Int32)?displayProperty=fullName> nach einem Aufruf von <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName> wiederzuverwenden, eine <xref:System.Security.Cryptography.CryptographicException> ausgelöst, oder es werden fehlerhafte Daten erstellt.

#### <a name="suggestion"></a>Vorschlag

Der Einfluss dieser Änderung sollte klein sein, da dies das erwartete Verhalten ist. Für Anwendungen, die vom bisherigen Verhalten abhängen, muss dieses Verhalten nicht übernommen werden, wenn Sie dem Abschnitt `<runtime>` der Anwendungskonfigurationsdatei die folgende Konfigurationseinstellung hinzufügen:

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=true"/>
</runtime>
```

Für Anwendungen, die für frühere Versionen von .NET Framework vorgesehen sind, aber unter .NET Framework 4.6.2 oder einer höheren Version ausgeführt werden, kann dieses Verhalten übernommen werden, indem dem `<runtime>`-Abschnitt der Anwendungskonfigurationsdatei die folgende Konfigurationseinstellung hinzugefügt wird:

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=false"/>
</runtime>
```

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.6.2       |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Security.Cryptography.AesCryptoServiceProvider.CreateDecryptor?displayProperty=nameWithType>
