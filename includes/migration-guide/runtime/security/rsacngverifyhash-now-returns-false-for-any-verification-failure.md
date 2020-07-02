---
ms.openlocfilehash: fa5cf2280cdd9535962568a6272d047d261eeba5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621209"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a><span data-ttu-id="0761e-101">RSACng.VerifyHash gibt nun FALSE für alle Überprüfungsfehler zurück</span><span class="sxs-lookup"><span data-stu-id="0761e-101">RSACng.VerifyHash now returns False for any verification failure</span></span>

#### <a name="details"></a><span data-ttu-id="0761e-102">Details</span><span class="sxs-lookup"><span data-stu-id="0761e-102">Details</span></span>

<span data-ttu-id="0761e-103">Ab .NET Framework 4.6.2 gibt diese Methode **FALSE** zurück, wenn die Signatur selbst ein ungültiges Format aufweist.</span><span class="sxs-lookup"><span data-stu-id="0761e-103">Starting with the .NET Framework 4.6.2, this method returns **False** if the signature itself is badly formatted.</span></span> <span data-ttu-id="0761e-104">Sie gibt nun für jeden Überprüfungsfehler FALSE zurück. In .NET Framework 4.6 und 4.6.1 löst diese Methode die Ausnahme <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> aus, wenn die Signatur selbst falsch formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="0761e-104">It now returns false for any verification failure.In the .NET Framework 4.6 and 4.6.1, the method throws a <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> if the signature itself is badly formatted.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0761e-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="0761e-105">Suggestion</span></span>

<span data-ttu-id="0761e-106">Jeder Code, dessen Ausführung von der Behandlung der <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>-Ausnahme abhängt, sollte stattdessen ausgeführt werden, wenn ein Validierungsfehler auftritt und die Methode **FALSE** zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="0761e-106">Any code whose execution depends on handling the <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> should instead execute if validation fails and the method returns **False**.</span></span>

| <span data-ttu-id="0761e-107">Name</span><span class="sxs-lookup"><span data-stu-id="0761e-107">Name</span></span>    | <span data-ttu-id="0761e-108">Wert</span><span class="sxs-lookup"><span data-stu-id="0761e-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0761e-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="0761e-109">Scope</span></span>   |<span data-ttu-id="0761e-110">Gering</span><span class="sxs-lookup"><span data-stu-id="0761e-110">Minor</span></span>|
|<span data-ttu-id="0761e-111">Version</span><span class="sxs-lookup"><span data-stu-id="0761e-111">Version</span></span>|<span data-ttu-id="0761e-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="0761e-112">4.6.2</span></span>|
|<span data-ttu-id="0761e-113">Typ</span><span class="sxs-lookup"><span data-stu-id="0761e-113">Type</span></span>|<span data-ttu-id="0761e-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="0761e-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0761e-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="0761e-115">Affected APIs</span></span>

-<xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|
