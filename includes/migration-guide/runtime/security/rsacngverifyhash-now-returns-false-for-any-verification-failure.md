---
ms.openlocfilehash: fc315faef750d93d914104dd568078aa3fc430d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "72887774"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a><span data-ttu-id="27974-101">RSACng.VerifyHash gibt nun FALSE für alle Überprüfungsfehler zurück</span><span class="sxs-lookup"><span data-stu-id="27974-101">RSACng.VerifyHash now returns False for any verification failure</span></span>

|   |   |
|---|---|
|<span data-ttu-id="27974-102">Details</span><span class="sxs-lookup"><span data-stu-id="27974-102">Details</span></span>|<span data-ttu-id="27974-103">Ab .NET Framework 4.6.2 gibt diese Methode **FALSE** zurück, wenn die Signatur selbst ein ungültiges Format aufweist.</span><span class="sxs-lookup"><span data-stu-id="27974-103">Starting with the .NET Framework 4.6.2, this method returns **False** if the signature itself is badly formatted.</span></span> <span data-ttu-id="27974-104">Sie gibt nun für jeden Überprüfungsfehler FALSE zurück. In .NET Framework 4.6 und 4.6.1 löst diese Methode die Ausnahme <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> aus, wenn die Signatur selbst falsch formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="27974-104">It now returns false for any verification failure.In the .NET Framework 4.6 and 4.6.1, the method throws a <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> if the signature itself is badly formatted.</span></span>|
|<span data-ttu-id="27974-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="27974-105">Suggestion</span></span>|<span data-ttu-id="27974-106">Jeder Code, dessen Ausführung von der Behandlung der <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>-Ausnahme abhängt, sollte stattdessen ausgeführt werden, wenn ein Validierungsfehler auftritt und die Methode **FALSE** zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="27974-106">Any code whose execution depends on handling the <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> should instead execute if validation fails and the method returns **False**.</span></span>|
|<span data-ttu-id="27974-107">`Scope`</span><span class="sxs-lookup"><span data-stu-id="27974-107">Scope</span></span>|<span data-ttu-id="27974-108">Nebenversion</span><span class="sxs-lookup"><span data-stu-id="27974-108">Minor</span></span>|
|<span data-ttu-id="27974-109">Version</span><span class="sxs-lookup"><span data-stu-id="27974-109">Version</span></span>|<span data-ttu-id="27974-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="27974-110">4.6.2</span></span>|
|<span data-ttu-id="27974-111">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="27974-111">Type</span></span>|<span data-ttu-id="27974-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="27974-112">Runtime</span></span>|
|<span data-ttu-id="27974-113">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="27974-113">Affected APIs</span></span>|<ul><li><xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|
