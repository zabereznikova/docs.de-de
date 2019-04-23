---
title: ICorProfilerFunctionControl::SetILInstrumentedCodeMap-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetILInstrumentedCodeMap
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetILInstrumentedCodeMap
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILInstrumentedCodeMap method [.NET Framework profiling]
- SetIILInstrumentedCodeMap method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: ecf56646-7e5f-46c4-8340-f3a04e88920f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b36439dd6fb882bb41c38e953cb7b1c5f2b93d30
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074104"
---
# <a name="icorprofilerfunctioncontrolsetilinstrumentedcodemap-method"></a><span data-ttu-id="371da-102">ICorProfilerFunctionControl::SetILInstrumentedCodeMap-Methode</span><span class="sxs-lookup"><span data-stu-id="371da-102">ICorProfilerFunctionControl::SetILInstrumentedCodeMap Method</span></span>
<span data-ttu-id="371da-103">Legt eine Codezuordnung für die angegebene Funktion mit den angegebenen Common Intermediate Language (CIL)-Zuordnungseinträgen fest.</span><span class="sxs-lookup"><span data-stu-id="371da-103">Sets a code map for the specified function by using the specified Common Intermediate Language (CIL) map entries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="371da-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="371da-104">Syntax</span></span>  
  
```  
HRESULT SetILInstrumentedCodeMap(  
    [in]   ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="371da-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="371da-105">Parameters</span></span>  
 `cILMapEntries`  
 <span data-ttu-id="371da-106">[in] Die Anzahl der Einträge in der Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="371da-106">[in] The number of entries in the map.</span></span>  
  
 `rgILMapEntries`  
 <span data-ttu-id="371da-107">[in] Das vom Aufrufer reserviertes Array von COR_IL_MAP-Einträgen.</span><span class="sxs-lookup"><span data-stu-id="371da-107">[in] The caller-allocated array of COR_IL_MAP  entries.</span></span> <span data-ttu-id="371da-108">Die Interpretation dieser Einträge ist dieselbe wie für die [ICorProfilerInfo:: SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="371da-108">The interpretation of these entries is the same as for the [ICorProfilerInfo::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="371da-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="371da-109">Remarks</span></span>  
 <span data-ttu-id="371da-110">Festlegen der Zuordnung durch Aufrufen dieser Methode ermöglicht dem Debugger zum Abrufen der Zuordnung durch Aufrufen von [icordebugilcode2:: Getinstrumentedilmap](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md).</span><span class="sxs-lookup"><span data-stu-id="371da-110">Setting the mapping by calling this method allows the debugger to retrieve the mapping by calling [ICorDebugILCode2::GetInstrumentedILMap](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md).</span></span> <span data-ttu-id="371da-111">Er kann die Zuordnung außerdem intern verwenden, wenn IL-Offsets für Stapelüberwachung und variable Lebensdauer berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="371da-111">It also allows the debugger to use the mapping internally when calculating IL offsets for stack traces and variable lifetimes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="371da-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="371da-112">Requirements</span></span>  
 <span data-ttu-id="371da-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="371da-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="371da-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="371da-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="371da-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="371da-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="371da-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="371da-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="371da-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="371da-117">See also</span></span>

- [<span data-ttu-id="371da-118">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="371da-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
