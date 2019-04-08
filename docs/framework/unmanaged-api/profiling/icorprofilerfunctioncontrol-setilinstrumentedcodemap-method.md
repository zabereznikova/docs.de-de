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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074104"
---
# <a name="icorprofilerfunctioncontrolsetilinstrumentedcodemap-method"></a><span data-ttu-id="9e944-102">ICorProfilerFunctionControl::SetILInstrumentedCodeMap-Methode</span><span class="sxs-lookup"><span data-stu-id="9e944-102">ICorProfilerFunctionControl::SetILInstrumentedCodeMap Method</span></span>
<span data-ttu-id="9e944-103">Legt eine Codezuordnung für die angegebene Funktion mit den angegebenen Common Intermediate Language (CIL)-Zuordnungseinträgen fest.</span><span class="sxs-lookup"><span data-stu-id="9e944-103">Sets a code map for the specified function by using the specified Common Intermediate Language (CIL) map entries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e944-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9e944-104">Syntax</span></span>  
  
```  
HRESULT SetILInstrumentedCodeMap(  
    [in]   ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e944-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9e944-105">Parameters</span></span>  
 `cILMapEntries`  
 <span data-ttu-id="9e944-106">[in] Die Anzahl der Einträge in der Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="9e944-106">[in] The number of entries in the map.</span></span>  
  
 `rgILMapEntries`  
 <span data-ttu-id="9e944-107">[in] Das vom Aufrufer reserviertes Array von COR_IL_MAP-Einträgen.</span><span class="sxs-lookup"><span data-stu-id="9e944-107">[in] The caller-allocated array of COR_IL_MAP  entries.</span></span> <span data-ttu-id="9e944-108">Die Interpretation dieser Einträge ist dieselbe wie für die [ICorProfilerInfo:: SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="9e944-108">The interpretation of these entries is the same as for the [ICorProfilerInfo::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e944-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9e944-109">Remarks</span></span>  
 <span data-ttu-id="9e944-110">Festlegen der Zuordnung durch Aufrufen dieser Methode ermöglicht dem Debugger zum Abrufen der Zuordnung durch Aufrufen von [icordebugilcode2:: Getinstrumentedilmap](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md).</span><span class="sxs-lookup"><span data-stu-id="9e944-110">Setting the mapping by calling this method allows the debugger to retrieve the mapping by calling [ICorDebugILCode2::GetInstrumentedILMap](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md).</span></span> <span data-ttu-id="9e944-111">Er kann die Zuordnung außerdem intern verwenden, wenn IL-Offsets für Stapelüberwachung und variable Lebensdauer berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="9e944-111">It also allows the debugger to use the mapping internally when calculating IL offsets for stack traces and variable lifetimes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e944-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9e944-112">Requirements</span></span>  
 <span data-ttu-id="9e944-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e944-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e944-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9e944-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9e944-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e944-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="9e944-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="9e944-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9e944-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e944-117">See also</span></span>

- [<span data-ttu-id="9e944-118">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9e944-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
