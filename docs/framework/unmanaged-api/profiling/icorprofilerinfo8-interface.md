---
title: ICorProfilerInfo8-Schnittstelle
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 210029ed1b1c7d780f3895f975f7a72227bbea80
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973820"
---
# <a name="icorprofilerinfo8-interface"></a><span data-ttu-id="d9c4a-102">ICorProfilerInfo8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d9c4a-102">ICorProfilerInfo8 Interface</span></span>

<span data-ttu-id="d9c4a-103">Eine Unterklasse von [ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) , die Methoden zum Abfragen von Informationen zu dynamischen Methoden bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="d9c4a-103">A subclass of [ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) that provides methods to query information about dynamic methods.</span></span>

## <a name="methods"></a><span data-ttu-id="d9c4a-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d9c4a-104">Methods</span></span>  

| <span data-ttu-id="d9c4a-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d9c4a-105">Method</span></span>|<span data-ttu-id="d9c4a-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d9c4a-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="d9c4a-107">Isfunctiondynamic-Methode</span><span class="sxs-lookup"><span data-stu-id="d9c4a-107">IsFunctionDynamic Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-isfunctiondynamic-method.md)| <span data-ttu-id="d9c4a-108">Bestimmt, ob einer Funktion keine zugeordneten Metadaten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="d9c4a-108">Determines if a function does not have associated metadata.</span></span>|
|[<span data-ttu-id="d9c4a-109">GetFunctionFromIP3-Methode</span><span class="sxs-lookup"><span data-stu-id="d9c4a-109">GetFunctionFromIP3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-getfunctionfromip3-method.md)| <span data-ttu-id="d9c4a-110">Ordnet einen Anweisungs Zeiger für verwalteten Code einem functionId-Wert zu.</span><span class="sxs-lookup"><span data-stu-id="d9c4a-110">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="d9c4a-111">Diese Methode funktioniert sowohl für dynamische als auch für nicht dynamische Methoden.</span><span class="sxs-lookup"><span data-stu-id="d9c4a-111">This method works for both dynamic and non-dynamic methods.</span></span> |
|[<span data-ttu-id="d9c4a-112">Getdynamicfunctioninfo-Methode</span><span class="sxs-lookup"><span data-stu-id="d9c4a-112">GetDynamicFunctionInfo Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-getdynamicfunctioninfo-method.md)| <span data-ttu-id="d9c4a-113">Ruft Informationen zu dynamischen Methoden ab.</span><span class="sxs-lookup"><span data-stu-id="d9c4a-113">Retrieves information about dynamic methods.</span></span> |

## <a name="requirements"></a><span data-ttu-id="d9c4a-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d9c4a-114">Requirements</span></span>  
<span data-ttu-id="d9c4a-115">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9c4a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="d9c4a-116">**Header:** Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="d9c4a-116">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="d9c4a-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d9c4a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
## <a name="see-also"></a><span data-ttu-id="d9c4a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9c4a-118">See also</span></span>
- [<span data-ttu-id="d9c4a-119">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="d9c4a-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
