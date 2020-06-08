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
ms.openlocfilehash: 738c98a0a37983faa71ea6e5eeaabb20639f604a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503137"
---
# <a name="icorprofilerfunctioncontrolsetilinstrumentedcodemap-method"></a><span data-ttu-id="ce250-102">ICorProfilerFunctionControl::SetILInstrumentedCodeMap-Methode</span><span class="sxs-lookup"><span data-stu-id="ce250-102">ICorProfilerFunctionControl::SetILInstrumentedCodeMap Method</span></span>
<span data-ttu-id="ce250-103">Legt eine Codezuordnung für die angegebene Funktion mit den angegebenen Common Intermediate Language (CIL)-Zuordnungseinträgen fest.</span><span class="sxs-lookup"><span data-stu-id="ce250-103">Sets a code map for the specified function by using the specified Common Intermediate Language (CIL) map entries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce250-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce250-104">Syntax</span></span>  
  
```cpp  
HRESULT SetILInstrumentedCodeMap(  
    [in]   ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce250-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ce250-105">Parameters</span></span>  
 `cILMapEntries`  
 <span data-ttu-id="ce250-106">[in] Die Anzahl der Einträge in der Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="ce250-106">[in] The number of entries in the map.</span></span>  
  
 `rgILMapEntries`  
 <span data-ttu-id="ce250-107">[in] Die vom Aufrufer reservierte Array mit COR_IL_MAP-Einträgen.</span><span class="sxs-lookup"><span data-stu-id="ce250-107">[in] The caller-allocated array of COR_IL_MAP  entries.</span></span> <span data-ttu-id="ce250-108">Die Interpretation dieser Einträge ist die gleiche wie für die [ICorProfilerInfo:: Setup](icorprofilerinfo-setilinstrumentedcodemap-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="ce250-108">The interpretation of these entries is the same as for the [ICorProfilerInfo::SetILInstrumentedCodeMap](icorprofilerinfo-setilinstrumentedcodemap-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce250-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ce250-109">Remarks</span></span>  
 <span data-ttu-id="ce250-110">Wenn die Zuordnung durch Aufrufen dieser Methode festgelegt wird, kann der Debugger die Zuordnung durch Aufrufen von [ICorDebugILCode2:: GetInstrumentedILMap](../debugging/icordebugilcode2-getinstrumentedilmap-method.md)abrufen.</span><span class="sxs-lookup"><span data-stu-id="ce250-110">Setting the mapping by calling this method allows the debugger to retrieve the mapping by calling [ICorDebugILCode2::GetInstrumentedILMap](../debugging/icordebugilcode2-getinstrumentedilmap-method.md).</span></span> <span data-ttu-id="ce250-111">Er kann die Zuordnung außerdem intern verwenden, wenn IL-Offsets für Stapelüberwachung und variable Lebensdauer berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="ce250-111">It also allows the debugger to use the mapping internally when calculating IL offsets for stack traces and variable lifetimes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce250-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ce250-112">Requirements</span></span>  
 <span data-ttu-id="ce250-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce250-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce250-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ce250-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ce250-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce250-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce250-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce250-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce250-117">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="ce250-117">See also</span></span>

- [<span data-ttu-id="ce250-118">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ce250-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
