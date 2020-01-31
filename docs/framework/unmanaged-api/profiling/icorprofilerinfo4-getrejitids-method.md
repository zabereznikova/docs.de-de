---
title: ICorProfilerInfo4::GetReJITIDs-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetReJITIDs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetReJITIDs
helpviewer_keywords:
- GetReJITIDs method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetReJITIDs method [.NET Framework profiling]
ms.assetid: 634ac28c-a5b7-4fc3-af84-256c24ca8177
topic_type:
- apiref
ms.openlocfilehash: 9069498a4f62f4d9dbb50a7075323b14c3cc5ab9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868446"
---
# <a name="icorprofilerinfo4getrejitids-method"></a><span data-ttu-id="f5e13-102">ICorProfilerInfo4::GetReJITIDs-Methode</span><span class="sxs-lookup"><span data-stu-id="f5e13-102">ICorProfilerInfo4::GetReJITIDs Method</span></span>
<span data-ttu-id="f5e13-103">Gibt ein Array von IDs zurück, die alle JIT-neu kompilierten Versionen der angegebenen Funktion identifizieren, die noch zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="f5e13-103">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span> <span data-ttu-id="f5e13-104">Dies schließt JIT-kompilierte Versionen von Funktionen ein, die anschließend wieder hergestellt, aber noch nicht freigegeben wurden (z. b. wenn die Anwendungsdomäne, die die wiederhergestellte Funktion enthält, noch verwendet wird).</span><span class="sxs-lookup"><span data-stu-id="f5e13-104">This includes JIT-recompiled versions of functions that have been subsequently reverted but not yet freed (for example, when the application domain that contains the reverted function is still in use).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5e13-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5e13-105">Syntax</span></span>  
  
```cpp
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5e13-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="f5e13-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="f5e13-107">in Der `FunctionID` der Funktions Instanz, für die Versionen aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f5e13-107">[in] The `FunctionID` of the function instance for which to enumerate versions.</span></span>  
  
 `cReJitIds`  
 <span data-ttu-id="f5e13-108">in Die Anzahl der im `reJitIds` Array zugeordneten JIT-neu kompilierten IDs.</span><span class="sxs-lookup"><span data-stu-id="f5e13-108">[in] The number of JIT-recompiled IDs allocated in the `reJitIds` array.</span></span>  
  
 `pcReJitIds`  
 <span data-ttu-id="f5e13-109">vorgenommen Die tatsächliche Anzahl der JIT-neu kompilierten IDs.</span><span class="sxs-lookup"><span data-stu-id="f5e13-109">[out] The actual number of JIT-recompiled IDs.</span></span>  
  
 `reJitIds`  
 <span data-ttu-id="f5e13-110">vorgenommen Ein vom Aufrufer zugewiesenes Array, das die JIT-neu kompilierten IDs für die angegebene Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="f5e13-110">[out] A caller-allocated array that will contain the JIT-recompiled IDs for the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5e13-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f5e13-111">Remarks</span></span>  
 <span data-ttu-id="f5e13-112">`GetReJITIDs` listet die aktiven JIT-neu kompilierten IDs für eine angegebene Funktions Instanz auf.</span><span class="sxs-lookup"><span data-stu-id="f5e13-112">`GetReJITIDs` enumerates the active JIT-recompiled IDs for a given function instance.</span></span> <span data-ttu-id="f5e13-113">Es folgt dem gleichen Verwendungs Muster wie andere `ICorProfilerInfo` Funktionen, die vom Aufrufer zugewiesene Puffer akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="f5e13-113">It follows the same usage pattern as other `ICorProfilerInfo` functions that accept caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5e13-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f5e13-114">Requirements</span></span>  
 <span data-ttu-id="f5e13-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5e13-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5e13-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f5e13-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f5e13-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5e13-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5e13-118">**.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5e13-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5e13-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5e13-119">See also</span></span>

- [<span data-ttu-id="f5e13-120">ICorProfilerInfo4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f5e13-120">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="f5e13-121">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f5e13-121">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="f5e13-122">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="f5e13-122">Profiling</span></span>](index.md)
