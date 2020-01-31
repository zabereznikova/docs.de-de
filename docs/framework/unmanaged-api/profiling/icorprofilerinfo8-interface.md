---
title: ICorProfilerInfo8-Schnittstelle
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 476bcbd91188e3ff9eb63f50cfa2118a440b1a69
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868316"
---
# <a name="icorprofilerinfo8-interface"></a><span data-ttu-id="b4429-102">ICorProfilerInfo8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4429-102">ICorProfilerInfo8 Interface</span></span>

<span data-ttu-id="b4429-103">Eine Unterklasse von [ICorProfilerInfo7](icorprofilerinfo7-interface.md) , die Methoden zum Abfragen von Informationen zu dynamischen Methoden bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="b4429-103">A subclass of [ICorProfilerInfo7](icorprofilerinfo7-interface.md) that provides methods to query information about dynamic methods.</span></span>

## <a name="methods"></a><span data-ttu-id="b4429-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="b4429-104">Methods</span></span>  

| <span data-ttu-id="b4429-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="b4429-105">Method</span></span>|<span data-ttu-id="b4429-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4429-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="b4429-107">Isfunctiondynamic-Methode</span><span class="sxs-lookup"><span data-stu-id="b4429-107">IsFunctionDynamic Method</span></span>](icorprofilerinfo8-isfunctiondynamic-method.md)| <span data-ttu-id="b4429-108">Bestimmt, ob einer Funktion keine zugeordneten Metadaten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="b4429-108">Determines if a function does not have associated metadata.</span></span>|
|[<span data-ttu-id="b4429-109">GetFunctionFromIP3-Methode</span><span class="sxs-lookup"><span data-stu-id="b4429-109">GetFunctionFromIP3 Method</span></span>](icorprofilerinfo8-getfunctionfromip3-method.md)| <span data-ttu-id="b4429-110">Ordnet einen Anweisungs Zeiger für verwalteten Code einem functionId-Wert zu.</span><span class="sxs-lookup"><span data-stu-id="b4429-110">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="b4429-111">Diese Methode funktioniert sowohl für dynamische als auch für nicht dynamische Methoden.</span><span class="sxs-lookup"><span data-stu-id="b4429-111">This method works for both dynamic and non-dynamic methods.</span></span> |
|[<span data-ttu-id="b4429-112">Getdynamicfunctioninfo-Methode</span><span class="sxs-lookup"><span data-stu-id="b4429-112">GetDynamicFunctionInfo Method</span></span>](icorprofilerinfo8-getdynamicfunctioninfo-method.md)| <span data-ttu-id="b4429-113">Ruft Informationen zu dynamischen Methoden ab.</span><span class="sxs-lookup"><span data-stu-id="b4429-113">Retrieves information about dynamic methods.</span></span> |

## <a name="requirements"></a><span data-ttu-id="b4429-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b4429-114">Requirements</span></span>  
<span data-ttu-id="b4429-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4429-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b4429-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b4429-116">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="b4429-117">**.NET Framework Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b4429-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b4429-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4429-118">See also</span></span>

- [<span data-ttu-id="b4429-119">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b4429-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
