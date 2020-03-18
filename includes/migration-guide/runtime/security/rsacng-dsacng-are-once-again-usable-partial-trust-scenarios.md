---
ms.openlocfilehash: 8b41e3234c00059ecb5088bbf2597611d7f139b8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857234"
---
### <a name="rsacng-and-dsacng-are-once-again-usable-in-partial-trust-scenarios"></a>„RSACng“ und „DSACng“ sind in Szenarios mit teilweiser Vertrauenswürdigkeit wieder verwendbar

|   |   |
|---|---|
|Details|CngLightup (das in einigen Krypto-APIs auf höherer Ebene verwendet wird, z.B. <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType>) und <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> erfordern in einigen Fällen volles Vertrauen. Dazu zählen P/Invoke-Aufrufe ohne gewährte <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType>-Berechtigungen sowie Codepfade, bei denen <xref:System.Security.Cryptography.CngKey?displayProperty=nameWithType> eine Berechtigungsanforderung für <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType> aufweist. Ab .NET Framework 4.6.2 wurde „CngLightup“ verwendet, um nach Möglichkeit zu <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> zu wechseln. In Folge schlugen teilweise vertrauenswürdige Apps fehl, die <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType> erfolgreich verwendeten, und lösten <xref:System.Security.SecurityException>-Ausnahmen aus. Durch diese Änderungen werden die erforderlichen Berechtigungen hinzugefügt, sodass alle Funktionen, die „CngLightup“ verwenden, über die erforderlichen Berechtigungen verfügen.|
|Vorschlag|Wenn diese Änderung in .NET Framework 4.6.2 sich negativ auf Ihre teilweise vertrauenswürdigen Apps ausgewirkt hat, führen Sie ein Upgrade auf .NET Framework 4.7.1 durch.|
|`Scope`|Edge|
|Version|4.6.2|
|Geben Sie Folgendes ein:|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Security.Cryptography.DSACng.%23ctor(System.Security.Cryptography.CngKey)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.Key?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.LegalKeySizes?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.CreateSignature(System.Byte[])?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.VerifySignature(System.Byte[],System.Byte[])?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.%23ctor(System.Security.Cryptography.CngKey)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.Key?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.Decrypt(System.Byte[],System.Security.Cryptography.RSAEncryptionPadding)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.SignHash(System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|
