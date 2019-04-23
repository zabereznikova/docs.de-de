---
ms.openlocfilehash: a93fbbd787aa50f080337a6170cf8f56d0d24e31
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236696"
---
### <a name="concurrentqueuettrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a><span data-ttu-id="a631c-101">ConcurrentQueue\<T>.TryPeek kann über einen out-Parameter einen fehlerhaften NULL-Wert zurückgeben</span><span class="sxs-lookup"><span data-stu-id="a631c-101">ConcurrentQueue\<T>.TryPeek can return an erroneous null via its out parameter</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a631c-102">Details</span><span class="sxs-lookup"><span data-stu-id="a631c-102">Details</span></span>|<span data-ttu-id="a631c-103">In einigen Multithreaded-Szenarien kann <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=name> „true“ zurückgeben, aber den Out-Parameter mit einem Nullwert füllen (anstelle des richtigen Werts).</span><span class="sxs-lookup"><span data-stu-id="a631c-103">In some multi-threaded scenarios, <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=name> can return true, but populate the out parameter with a null value (instead of the correct, peeked value).</span></span>|
|<span data-ttu-id="a631c-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="a631c-104">Suggestion</span></span>|<span data-ttu-id="a631c-105">Dieses Problem wurde in .NET Framework 4.5.1 behoben.</span><span class="sxs-lookup"><span data-stu-id="a631c-105">This issue is fixed in the .NET Framework 4.5.1.</span></span> <span data-ttu-id="a631c-106">Dieses Problem wird durch ein Upgrade auf diese .NET Framework-Version behoben.</span><span class="sxs-lookup"><span data-stu-id="a631c-106">Upgrading to that Framework will solve the issue.</span></span>|
|<span data-ttu-id="a631c-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="a631c-107">Scope</span></span>|<span data-ttu-id="a631c-108">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="a631c-108">Major</span></span>|
|<span data-ttu-id="a631c-109">Version</span><span class="sxs-lookup"><span data-stu-id="a631c-109">Version</span></span>|<span data-ttu-id="a631c-110">4.5</span><span class="sxs-lookup"><span data-stu-id="a631c-110">4.5</span></span>|
|<span data-ttu-id="a631c-111">Typ</span><span class="sxs-lookup"><span data-stu-id="a631c-111">Type</span></span>|<span data-ttu-id="a631c-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="a631c-112">Runtime</span></span>|
|<span data-ttu-id="a631c-113">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a631c-113">Affected APIs</span></span>|<ul><li><xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType></li></ul>|
