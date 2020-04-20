---
ms.openlocfilehash: b3bf169f60279d245568367afb0bfe004c4ebcd7
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "81275367"
---
### <a name="rsacng-and-dsacng-are-once-again-usable-in-partial-trust-scenarios"></a>„RSACng“ und „DSACng“ sind in Szenarios mit teilweiser Vertrauenswürdigkeit wieder verwendbar

|   |   |
|---|---|
|Details|CngLightup (das in einigen Krypto-APIs auf höherer Ebene verwendet wird, z.B. <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType>) und <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> erfordern in einigen Fällen volles Vertrauen. Dazu zählen P/Invoke-Aufrufe ohne gewährte <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType>-Berechtigungen sowie Codepfade, bei denen <xref:System.Security.Cryptography.CngKey?displayProperty=nameWithType> eine Berechtigungsanforderung für <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType> aufweist. Ab .NET Framework 4.6.2 wurde „CngLightup“ verwendet, um nach Möglichkeit zu <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> zu wechseln. In Folge schlugen teilweise vertrauenswürdige Apps fehl, die <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType> erfolgreich verwendeten, und lösten <xref:System.Security.SecurityException>-Ausnahmen aus. Durch diese Änderungen werden die erforderlichen Berechtigungen hinzugefügt, sodass alle Funktionen, die „CngLightup“ verwenden, über die erforderlichen Berechtigungen verfügen.|
|Vorschlag|Wenn diese Änderung in .NET Framework 4.6.2 sich negativ auf Ihre teilweise vertrauenswürdigen Apps ausgewirkt hat, führen Sie ein Upgrade auf .NET Framework 4.7.1 durch.|
|`Scope`|Edge|
|Version|4.6.2|
|Geben Sie Folgendes ein:|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Security.Cryptography.DSACng.%23ctor(System.Security.Cryptography.CngKey)></li><li><xref:System.Security.Cryptography.DSACng.Key?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.LegalKeySizes?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.CreateSignature(System.Byte[])?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.VerifySignature(System.Byte[],System.Byte[])?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.%23ctor(System.Security.Cryptography.CngKey)></li><li><xref:System.Security.Cryptography.RSACng.Key?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.Decrypt(System.Byte[],System.Security.Cryptography.RSAEncryptionPadding)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.SignHash(System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|
