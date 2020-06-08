---
title: ICorProfilerInfo8-Schnittstelle
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 2cca915eda44d73aea7469e5f752c57309c2300d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495163"
---
# <a name="icorprofilerinfo8-interface"></a><span data-ttu-id="bfba3-102">ICorProfilerInfo8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bfba3-102">ICorProfilerInfo8 Interface</span></span>

<span data-ttu-id="bfba3-103">Eine Unterklasse von [ICorProfilerInfo7](icorprofilerinfo7-interface.md) , die Methoden zum Abfragen von Informationen zu dynamischen Methoden bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="bfba3-103">A subclass of [ICorProfilerInfo7](icorprofilerinfo7-interface.md) that provides methods to query information about dynamic methods.</span></span>

## <a name="methods"></a><span data-ttu-id="bfba3-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="bfba3-104">Methods</span></span>  

| <span data-ttu-id="bfba3-105">Methode</span><span class="sxs-lookup"><span data-stu-id="bfba3-105">Method</span></span>|<span data-ttu-id="bfba3-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bfba3-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="bfba3-107">IsFunctionDynamic-Methode</span><span class="sxs-lookup"><span data-stu-id="bfba3-107">IsFunctionDynamic Method</span></span>](icorprofilerinfo8-isfunctiondynamic-method.md)| <span data-ttu-id="bfba3-108">Bestimmt, ob einer Funktion keine zugeordneten Metadaten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="bfba3-108">Determines if a function does not have associated metadata.</span></span>|
|[<span data-ttu-id="bfba3-109">GetFunctionFromIP3-Methode</span><span class="sxs-lookup"><span data-stu-id="bfba3-109">GetFunctionFromIP3 Method</span></span>](icorprofilerinfo8-getfunctionfromip3-method.md)| <span data-ttu-id="bfba3-110">Ordnet einen Anweisungs Zeiger für verwalteten Code einem functionId-Wert zu.</span><span class="sxs-lookup"><span data-stu-id="bfba3-110">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="bfba3-111">Diese Methode funktioniert sowohl für dynamische als auch für nicht dynamische Methoden.</span><span class="sxs-lookup"><span data-stu-id="bfba3-111">This method works for both dynamic and non-dynamic methods.</span></span> |
|[<span data-ttu-id="bfba3-112">GetDynamicFunctionInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="bfba3-112">GetDynamicFunctionInfo Method</span></span>](icorprofilerinfo8-getdynamicfunctioninfo-method.md)| <span data-ttu-id="bfba3-113">Ruft Informationen zu dynamischen Methoden ab.</span><span class="sxs-lookup"><span data-stu-id="bfba3-113">Retrieves information about dynamic methods.</span></span> |

## <a name="requirements"></a><span data-ttu-id="bfba3-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bfba3-114">Requirements</span></span>  
<span data-ttu-id="bfba3-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfba3-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="bfba3-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bfba3-116">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="bfba3-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bfba3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="bfba3-118">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="bfba3-118">See also</span></span>

- [<span data-ttu-id="bfba3-119">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="bfba3-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
