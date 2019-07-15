---
ms.openlocfilehash: 7d60578ac2913037e1cdeda329f06f9a4986574d
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67857549"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a><span data-ttu-id="2d9ed-101">RSACng.VerifyHash gibt nun FALSE für alle Überprüfungsfehler zurück</span><span class="sxs-lookup"><span data-stu-id="2d9ed-101">RSACng.VerifyHash now returns False for any verification failure</span></span>

|   |   |
|---|---|
|<span data-ttu-id="2d9ed-102">Details</span><span class="sxs-lookup"><span data-stu-id="2d9ed-102">Details</span></span>|<span data-ttu-id="2d9ed-103">Ab .NET Framework 4.6.2 gibt diese Methode <strong>FALSE</strong> zurück, wenn die Signatur selbst ein ungültiges Format aufweist.</span><span class="sxs-lookup"><span data-stu-id="2d9ed-103">Starting with the .NET Framework 4.6.2, this method returns <strong>False</strong> if the signature itself is badly formatted.</span></span> <span data-ttu-id="2d9ed-104">Sie gibt nun für jeden Überprüfungsfehler FALSE zurück. In .NET Framework 4.6 und 4.6.1 löst diese Methode die Ausnahme <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> aus, wenn die Signatur selbst falsch formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="2d9ed-104">It now returns false for any verification failure.In the .NET Framework 4.6 and 4.6.1, the method throws a <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> if the signature itself is badly formatted.</span></span>|
|<span data-ttu-id="2d9ed-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="2d9ed-105">Suggestion</span></span>|<span data-ttu-id="2d9ed-106">Jeder Code, dessen Ausführung von der Behandlung der <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>-Ausnahme abhängt, sollte stattdessen ausgeführt werden, wenn ein Validierungsfehler auftritt und die Methode <strong>FALSE</strong> zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="2d9ed-106">Any code whose execution depends on handling the <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> should instead execute if validation fails and the method returns <strong>False</strong>.</span></span>|
|<span data-ttu-id="2d9ed-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="2d9ed-107">Scope</span></span>|<span data-ttu-id="2d9ed-108">Gering</span><span class="sxs-lookup"><span data-stu-id="2d9ed-108">Minor</span></span>|
|<span data-ttu-id="2d9ed-109">Version</span><span class="sxs-lookup"><span data-stu-id="2d9ed-109">Version</span></span>|<span data-ttu-id="2d9ed-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="2d9ed-110">4.6.2</span></span>|
|<span data-ttu-id="2d9ed-111">Typ</span><span class="sxs-lookup"><span data-stu-id="2d9ed-111">Type</span></span>|<span data-ttu-id="2d9ed-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="2d9ed-112">Runtime</span></span>|
|<span data-ttu-id="2d9ed-113">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="2d9ed-113">Affected APIs</span></span>|<ul><li><xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|

