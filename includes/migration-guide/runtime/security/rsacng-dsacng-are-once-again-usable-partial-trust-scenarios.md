---
ms.openlocfilehash: 4788f5b80306116e63ee56584d65b862ce0606ee
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497270"
---
### <a name="rsacng-and-dsacng-are-once-again-usable-in-partial-trust-scenarios"></a><span data-ttu-id="b217c-101">„RSACng“ und „DSACng“ sind in Szenarios mit teilweiser Vertrauenswürdigkeit wieder verwendbar</span><span class="sxs-lookup"><span data-stu-id="b217c-101">RSACng and DSACng are once again usable in Partial Trust scenarios</span></span>

#### <a name="details"></a><span data-ttu-id="b217c-102">Details</span><span class="sxs-lookup"><span data-stu-id="b217c-102">Details</span></span>

<span data-ttu-id="b217c-103">CngLightup (das in einigen Krypto-APIs auf höherer Ebene verwendet wird, z.B. <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType>) und <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> erfordern in einigen Fällen volles Vertrauen.</span><span class="sxs-lookup"><span data-stu-id="b217c-103">CngLightup (used in several higher-level crypto apis, such as <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType>) and <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> in some cases rely on full trust.</span></span> <span data-ttu-id="b217c-104">Dazu zählen P/Invoke-Aufrufe ohne gewährte <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType>-Berechtigungen sowie Codepfade, bei denen <xref:System.Security.Cryptography.CngKey?displayProperty=nameWithType> eine Berechtigungsanforderung für <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType> aufweist.</span><span class="sxs-lookup"><span data-stu-id="b217c-104">These include P/Invokes without asserting <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType> permissions, and code paths where <xref:System.Security.Cryptography.CngKey?displayProperty=nameWithType> has permission demands for <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b217c-105">Ab .NET Framework 4.6.2 wurde „CngLightup“ verwendet, um nach Möglichkeit zu <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="b217c-105">Starting with the .NET Framework 4.6.2, CngLightup was used to switch to <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> wherever possible.</span></span> <span data-ttu-id="b217c-106">In Folge schlugen teilweise vertrauenswürdige Apps fehl, die <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType> erfolgreich verwendeten, und lösten <xref:System.Security.SecurityException>-Ausnahmen aus. Durch diese Änderungen werden die erforderlichen Berechtigungen hinzugefügt, sodass alle Funktionen, die „CngLightup“ verwenden, über die erforderlichen Berechtigungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="b217c-106">As a result, partial trust apps that successfully used <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType> began to fail and throw <xref:System.Security.SecurityException> exceptions.This change adds the required asserts so that all functions using CngLightup have the required permissions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b217c-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="b217c-107">Suggestion</span></span>

<span data-ttu-id="b217c-108">Wenn diese Änderung in .NET Framework 4.6.2 sich negativ auf Ihre teilweise vertrauenswürdigen Apps ausgewirkt hat, führen Sie ein Upgrade auf .NET Framework 4.7.1 durch.</span><span class="sxs-lookup"><span data-stu-id="b217c-108">If this change in the .NET Framework 4.6.2 has negatively impacted your partial trust apps, upgrade to the .NET Framework 4.7.1.</span></span>

| <span data-ttu-id="b217c-109">Name</span><span class="sxs-lookup"><span data-stu-id="b217c-109">Name</span></span>    | <span data-ttu-id="b217c-110">Wert</span><span class="sxs-lookup"><span data-stu-id="b217c-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b217c-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="b217c-111">Scope</span></span>   |<span data-ttu-id="b217c-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b217c-112">Edge</span></span>|
|<span data-ttu-id="b217c-113">Version</span><span class="sxs-lookup"><span data-stu-id="b217c-113">Version</span></span>|<span data-ttu-id="b217c-114">4.6.2</span><span class="sxs-lookup"><span data-stu-id="b217c-114">4.6.2</span></span>|
|<span data-ttu-id="b217c-115">Typ</span><span class="sxs-lookup"><span data-stu-id="b217c-115">Type</span></span>|<span data-ttu-id="b217c-116">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="b217c-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="b217c-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="b217c-117">Affected APIs</span></span>

- <xref:System.Security.Cryptography.DSACng.%23ctor(System.Security.Cryptography.CngKey)>
- <xref:System.Security.Cryptography.DSACng.Key?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSACng.LegalKeySizes?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSACng.CreateSignature(System.Byte[])?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSACng.VerifySignature(System.Byte[],System.Byte[])?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACng.%23ctor(System.Security.Cryptography.CngKey)>
- <xref:System.Security.Cryptography.RSACng.Key?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACng.Decrypt(System.Byte[],System.Security.Cryptography.RSAEncryptionPadding)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACng.SignHash(System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.DSACng.#ctor(System.Security.Cryptography.CngKey)`
- `P:System.Security.Cryptography.DSACng.Key`
- `P:System.Security.Cryptography.DSACng.LegalKeySizes`
- `M:System.Security.Cryptography.DSACng.CreateSignature(System.Byte[])`
- `M:System.Security.Cryptography.DSACng.VerifySignature(System.Byte[],System.Byte[])`
- `M:System.Security.Cryptography.RSACng.#ctor(System.Security.Cryptography.CngKey)`
- `P:System.Security.Cryptography.RSACng.Key`
- `M:System.Security.Cryptography.RSACng.Decrypt(System.Byte[],System.Security.Cryptography.RSAEncryptionPadding)`
- `M:System.Security.Cryptography.RSACng.SignHash(System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)`

-->
