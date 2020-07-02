---
ms.openlocfilehash: 02a15f6b9c02002b60c568b9e1d871af49744092
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622050"
---
### <a name="concurrentqueuelttgttrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a><span data-ttu-id="ff7cf-101">ConcurrentQueue&lt;T&gt;.TryPeek kann über einen out-Parameter einen fehlerhaften NULL-Wert zurückgeben</span><span class="sxs-lookup"><span data-stu-id="ff7cf-101">ConcurrentQueue&lt;T&gt;.TryPeek can return an erroneous null via its out parameter</span></span>

#### <a name="details"></a><span data-ttu-id="ff7cf-102">Details</span><span class="sxs-lookup"><span data-stu-id="ff7cf-102">Details</span></span>

<span data-ttu-id="ff7cf-103">In einigen Multithreaded-Szenarien kann <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=fullName> „true“ zurückgeben, aber den Out-Parameter mit einem Nullwert füllen (anstelle des richtigen Werts).</span><span class="sxs-lookup"><span data-stu-id="ff7cf-103">In some multi-threaded scenarios, <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=fullName> can return true, but populate the out parameter with a null value (instead of the correct, peeked value).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ff7cf-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="ff7cf-104">Suggestion</span></span>

<span data-ttu-id="ff7cf-105">Dieses Problem wurde in .NET Framework 4.5.1 behoben.</span><span class="sxs-lookup"><span data-stu-id="ff7cf-105">This issue is fixed in the .NET Framework 4.5.1.</span></span> <span data-ttu-id="ff7cf-106">Dieses Problem wird durch ein Upgrade auf diese .NET Framework-Version behoben.</span><span class="sxs-lookup"><span data-stu-id="ff7cf-106">Upgrading to that Framework will solve the issue.</span></span>

| <span data-ttu-id="ff7cf-107">name</span><span class="sxs-lookup"><span data-stu-id="ff7cf-107">Name</span></span>    | <span data-ttu-id="ff7cf-108">Wert</span><span class="sxs-lookup"><span data-stu-id="ff7cf-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ff7cf-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="ff7cf-109">Scope</span></span>   |<span data-ttu-id="ff7cf-110">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="ff7cf-110">Major</span></span>|
|<span data-ttu-id="ff7cf-111">Version</span><span class="sxs-lookup"><span data-stu-id="ff7cf-111">Version</span></span>|<span data-ttu-id="ff7cf-112">4.5</span><span class="sxs-lookup"><span data-stu-id="ff7cf-112">4.5</span></span>|
|<span data-ttu-id="ff7cf-113">Typ</span><span class="sxs-lookup"><span data-stu-id="ff7cf-113">Type</span></span>|<span data-ttu-id="ff7cf-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="ff7cf-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ff7cf-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="ff7cf-115">Affected APIs</span></span>

-<xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType></li></ul>|
