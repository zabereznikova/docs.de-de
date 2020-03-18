---
ms.openlocfilehash: 1687b1b9a1a6861f9569a0e29426de7f32ffc32b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804529"
---
### <a name="il-ret-not-allowed-in-a-try-region"></a><span data-ttu-id="4f31c-101">Die IL-ret-Anweisung ist in einem try-Block nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="4f31c-101">IL ret not allowed in a try region</span></span>

|   |   |
|---|---|
|<span data-ttu-id="4f31c-102">Details</span><span class="sxs-lookup"><span data-stu-id="4f31c-102">Details</span></span>|<span data-ttu-id="4f31c-103">Im Gegensatz zum JIT64-Compiler lässt (in .NET Framework 4.6 verwendets) RyuJIT keine IL-ret-Anweisung in einem „try“-Block zu.</span><span class="sxs-lookup"><span data-stu-id="4f31c-103">Unlike the JIT64 just-in-time compiler, RyuJIT (used in .NET Framework 4.6) does not allow an IL ret instruction in a try region.</span></span> <span data-ttu-id="4f31c-104">Eine Rückgabe innerhalb eines try-Block ist gemäß der ECMA-335-Spezifikation nicht zulässig, und kein bekannter verwalteter Compiler generiert eine solche IL.</span><span class="sxs-lookup"><span data-stu-id="4f31c-104">Returning from a try region is disallowed by the ECMA-335 specification, and no known managed compiler generates such IL.</span></span> <span data-ttu-id="4f31c-105">Allerdings führt der JIT64-Compiler solche IL aus, wenn sie mithilfe von Reflektionsausgabe generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="4f31c-105">However, the JIT64 compiler will execute such IL if it is generated using reflection emit.</span></span>|
|<span data-ttu-id="4f31c-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="4f31c-106">Suggestion</span></span>|<span data-ttu-id="4f31c-107">Wenn eine App eine IL generiert, die einen „ret“-Opcode in einem „try“-Block enthält, kann die App auf .NET Framework 4.5 ausgelegt werden, um den alten JIT-Compiler zu verwenden und dieses Problem zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="4f31c-107">If an app is generating IL that includes a ret opcode in a try region, the app may target .NET Framework 4.5 to use the old JIT and avoid this break.</span></span> <span data-ttu-id="4f31c-108">Alternativ kann die generierte IL aktualisiert und nach dem try-Block zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4f31c-108">Alternatively, the generated IL may be updated to return after the try region.</span></span>|
|<span data-ttu-id="4f31c-109">`Scope`</span><span class="sxs-lookup"><span data-stu-id="4f31c-109">Scope</span></span>|<span data-ttu-id="4f31c-110">Edge</span><span class="sxs-lookup"><span data-stu-id="4f31c-110">Edge</span></span>|
|<span data-ttu-id="4f31c-111">Version</span><span class="sxs-lookup"><span data-stu-id="4f31c-111">Version</span></span>|<span data-ttu-id="4f31c-112">4.6</span><span class="sxs-lookup"><span data-stu-id="4f31c-112">4.6</span></span>|
|<span data-ttu-id="4f31c-113">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="4f31c-113">Type</span></span>|<span data-ttu-id="4f31c-114">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="4f31c-114">Retargeting</span></span>|
