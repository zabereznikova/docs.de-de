---
ms.openlocfilehash: 060da3ebc60057554fd572bd2569652afee6bd0f
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761079"
---
### <a name="il-ret-not-allowed-in-a-try-region"></a><span data-ttu-id="e018a-101">Die IL-ret-Anweisung ist in einem try-Block nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="e018a-101">IL ret not allowed in a try region</span></span>

|   |   |
|---|---|
|<span data-ttu-id="e018a-102">Details</span><span class="sxs-lookup"><span data-stu-id="e018a-102">Details</span></span>|<span data-ttu-id="e018a-103">Im Gegensatz zum JIT64-Compiler lässt (in .NET Framework 4.6 verwendets) RyuJIT keine IL-ret-Anweisung in einem „try“-Block zu.</span><span class="sxs-lookup"><span data-stu-id="e018a-103">Unlike the JIT64 just-in-time compiler, RyuJIT (used in .NET Framework 4.6) does not allow an IL ret instruction in a try region.</span></span> <span data-ttu-id="e018a-104">Eine Rückgabe innerhalb eines try-Block ist gemäß der ECMA-335-Spezifikation nicht zulässig, und kein bekannter verwalteter Compiler generiert eine solche IL.</span><span class="sxs-lookup"><span data-stu-id="e018a-104">Returning from a try region is disallowed by the ECMA-335 specification, and no known managed compiler generates such IL.</span></span> <span data-ttu-id="e018a-105">Allerdings führt der JIT64-Compiler solche IL aus, wenn sie mithilfe von Reflektionsausgabe generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="e018a-105">However, the JIT64 compiler will execute such IL if it is generated using reflection emit.</span></span>|
|<span data-ttu-id="e018a-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="e018a-106">Suggestion</span></span>|<span data-ttu-id="e018a-107">Wenn eine App eine IL generiert, die einen „ret“-Opcode in einem „try“-Block enthält, kann die App auf .NET Framework 4.5 ausgelegt werden, um den alten JIT-Compiler zu verwenden und dieses Problem zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="e018a-107">If an app is generating IL that includes a ret opcode in a try region, the app may target .NET Framework 4.5 to use the old JIT and avoid this break.</span></span> <span data-ttu-id="e018a-108">Alternativ kann die generierte IL aktualisiert und nach dem try-Block zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e018a-108">Alternatively, the generated IL may be updated to return after the try region.</span></span>|
|<span data-ttu-id="e018a-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="e018a-109">Scope</span></span>|<span data-ttu-id="e018a-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e018a-110">Edge</span></span>|
|<span data-ttu-id="e018a-111">Version</span><span class="sxs-lookup"><span data-stu-id="e018a-111">Version</span></span>|<span data-ttu-id="e018a-112">4.6</span><span class="sxs-lookup"><span data-stu-id="e018a-112">4.6</span></span>|
|<span data-ttu-id="e018a-113">Typ</span><span class="sxs-lookup"><span data-stu-id="e018a-113">Type</span></span>|<span data-ttu-id="e018a-114">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="e018a-114">Retargeting</span></span>|

