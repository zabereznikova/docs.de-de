---
ms.openlocfilehash: 4d410811095786b33580d25f6c6eab3ac2f27148
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616063"
---
### <a name="resolveassemblyreference-task-now-warns-of-dependencies-with-the-wrong-architecture"></a><span data-ttu-id="ec39c-101">Die ResolveAssemblyReference-Aufgabe warnt jetzt vor Abhängigkeiten von der falschen Architektur</span><span class="sxs-lookup"><span data-stu-id="ec39c-101">ResolveAssemblyReference task now warns of dependencies with the wrong architecture</span></span>

#### <a name="details"></a><span data-ttu-id="ec39c-102">Details</span><span class="sxs-lookup"><span data-stu-id="ec39c-102">Details</span></span>

<span data-ttu-id="ec39c-103">Die Aufgabe gibt die Warnung MSB3270 aus, die angibt, dass ein Verweis oder eine seiner Abhängigkeiten nicht der Architektur der App entspricht.</span><span class="sxs-lookup"><span data-stu-id="ec39c-103">The task emits a warning, MSB3270, which indicates that a reference or any of its dependencies does not match the app's architecture.</span></span> <span data-ttu-id="ec39c-104">Dies erfolgt z. B., wenn eine App, die mit der `AnyCPU`-Option kompiliert wurde, einen x86-Verweis enthält.</span><span class="sxs-lookup"><span data-stu-id="ec39c-104">For example, this occurs if an app that was compiled with the `AnyCPU` option includes an x86 reference.</span></span> <span data-ttu-id="ec39c-105">Ein solches Szenario kann einen App-Fehler zur Laufzeit ergeben (in diesem Fall, wenn die App als x64-Prozess bereitgestellt wird).</span><span class="sxs-lookup"><span data-stu-id="ec39c-105">Such a scenario could result in an app failure at run time (in this case, if the app is deployed as an x64 process).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ec39c-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="ec39c-106">Suggestion</span></span>

<span data-ttu-id="ec39c-107">Es gibt zwei Bereiche mit Auswirkungen:</span><span class="sxs-lookup"><span data-stu-id="ec39c-107">There are two areas of impact:</span></span>

- <span data-ttu-id="ec39c-108">Bei der Neukompilierung werden Warnungen generiert, die nicht angezeigt wurden, als die App mit einer früheren Version von MSBuild kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="ec39c-108">Recompilation generates warnings that did not appear when the app was compiled under a previous version of MSBuild.</span></span> <span data-ttu-id="ec39c-109">Da die Warnung eine potenzielle Quelle des Laufzeitfehlers angibt, sollte sie untersucht werden.</span><span class="sxs-lookup"><span data-stu-id="ec39c-109">However, because the warning identifies a possible source of runtime failure, it should be investigated and addressed.</span></span>
- <span data-ttu-id="ec39c-110">Wenn Warnungen wie Fehler behandelt werden, kann die Anwendung nicht kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="ec39c-110">If warnings are treated as errors, the app will fail to compile.</span></span>

| <span data-ttu-id="ec39c-111">name</span><span class="sxs-lookup"><span data-stu-id="ec39c-111">Name</span></span>    | <span data-ttu-id="ec39c-112">Wert</span><span class="sxs-lookup"><span data-stu-id="ec39c-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ec39c-113">Bereich</span><span class="sxs-lookup"><span data-stu-id="ec39c-113">Scope</span></span>   | <span data-ttu-id="ec39c-114">Gering</span><span class="sxs-lookup"><span data-stu-id="ec39c-114">Minor</span></span>       |
| <span data-ttu-id="ec39c-115">Version</span><span class="sxs-lookup"><span data-stu-id="ec39c-115">Version</span></span> | <span data-ttu-id="ec39c-116">4.5.1</span><span class="sxs-lookup"><span data-stu-id="ec39c-116">4.5.1</span></span>       |
| <span data-ttu-id="ec39c-117">Typ</span><span class="sxs-lookup"><span data-stu-id="ec39c-117">Type</span></span>    | <span data-ttu-id="ec39c-118">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="ec39c-118">Retargeting</span></span> |
