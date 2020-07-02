---
ms.openlocfilehash: e92cbb7decb5e530bbf611cec26ce03a05e06eb3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622245"
---
### <a name="rsacng-and-dsacng-are-once-again-usable-in-partial-trust-scenarios"></a>„RSACng“ und „DSACng“ sind in Szenarios mit teilweiser Vertrauenswürdigkeit wieder verwendbar

#### <a name="details"></a>Details

CngLightup (das in einigen Krypto-APIs auf höherer Ebene verwendet wird, z.B. <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType>) und <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> erfordern in einigen Fällen volles Vertrauen. Dazu zählen P/Invoke-Aufrufe ohne gewährte <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType>-Berechtigungen sowie Codepfade, bei denen <xref:System.Security.Cryptography.CngKey?displayProperty=nameWithType> eine Berechtigungsanforderung für <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType> aufweist. Ab .NET Framework 4.6.2 wurde „CngLightup“ verwendet, um nach Möglichkeit zu <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> zu wechseln. In Folge schlugen teilweise vertrauenswürdige Apps fehl, die <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType> erfolgreich verwendeten, und lösten <xref:System.Security.SecurityException>-Ausnahmen aus. Durch diese Änderungen werden die erforderlichen Berechtigungen hinzugefügt, sodass alle Funktionen, die „CngLightup“ verwenden, über die erforderlichen Berechtigungen verfügen.

#### <a name="suggestion"></a>Vorschlag

Wenn diese Änderung in .NET Framework 4.6.2 sich negativ auf Ihre teilweise vertrauenswürdigen Apps ausgewirkt hat, führen Sie ein Upgrade auf .NET Framework 4.7.1 durch.

| Name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.6.2|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Security.Cryptography.DSACng.%23ctor(System.Security.Cryptography.CngKey)></li><li><xref:System.Security.Cryptography.DSACng.Key?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.LegalKeySizes?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.CreateSignature(System.Byte[])?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.VerifySignature(System.Byte[],System.Byte[])?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.%23ctor(System.Security.Cryptography.CngKey)></li><li><xref:System.Security.Cryptography.RSACng.Key?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.Decrypt(System.Byte[],System.Security.Cryptography.RSAEncryptionPadding)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.SignHash(System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|
