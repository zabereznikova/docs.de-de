---
title: ICorProfilerInfo8-Schnittstelle
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 2baa33a7a3527392d8095b5d0ec7ad6af8a71a8e
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928933"
---
# <a name="icorprofilerinfo8-interface"></a><span data-ttu-id="f6814-102">ICorProfilerInfo8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f6814-102">ICorProfilerInfo8 Interface</span></span>

<span data-ttu-id="f6814-103">Eine Unterklasse von [ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) , die Methoden zum Abfragen von Informationen zu dynamischen Methoden bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f6814-103">A subclass of [ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) that provides methods to query information about dynamic methods.</span></span>

## <a name="methods"></a><span data-ttu-id="f6814-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f6814-104">Methods</span></span>  

| <span data-ttu-id="f6814-105">Methode</span><span class="sxs-lookup"><span data-stu-id="f6814-105">Method</span></span>|<span data-ttu-id="f6814-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f6814-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="f6814-107">Isfunctiondynamic-Methode</span><span class="sxs-lookup"><span data-stu-id="f6814-107">IsFunctionDynamic Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-isfunctiondynamic-method.md)| <span data-ttu-id="f6814-108">Bestimmt, ob einer Funktion keine zugeordneten Metadaten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="f6814-108">Determines if a function does not have associated metadata.</span></span>|
|[<span data-ttu-id="f6814-109">GetFunctionFromIP3-Methode</span><span class="sxs-lookup"><span data-stu-id="f6814-109">GetFunctionFromIP3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-getfunctionfromip3-method.md)| <span data-ttu-id="f6814-110">Ordnet einen Anweisungs Zeiger für verwalteten Code einem functionId-Wert zu.</span><span class="sxs-lookup"><span data-stu-id="f6814-110">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="f6814-111">Diese Methode funktioniert sowohl für dynamische als auch für nicht dynamische Methoden.</span><span class="sxs-lookup"><span data-stu-id="f6814-111">This method works for both dynamic and non-dynamic methods.</span></span> |
|[<span data-ttu-id="f6814-112">Getdynamicfunctioninfo-Methode</span><span class="sxs-lookup"><span data-stu-id="f6814-112">GetDynamicFunctionInfo Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-getdynamicfunctioninfo-method.md)| <span data-ttu-id="f6814-113">Ruft Informationen zu dynamischen Methoden ab.</span><span class="sxs-lookup"><span data-stu-id="f6814-113">Retrieves information about dynamic methods.</span></span> |

## <a name="requirements"></a><span data-ttu-id="f6814-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f6814-114">Requirements</span></span>  
<span data-ttu-id="f6814-115">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6814-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="f6814-116">**Header:** Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="f6814-116">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="f6814-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f6814-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="f6814-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6814-118">See also</span></span>

- [<span data-ttu-id="f6814-119">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f6814-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
