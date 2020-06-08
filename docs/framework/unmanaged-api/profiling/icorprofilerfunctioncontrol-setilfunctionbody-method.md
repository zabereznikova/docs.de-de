---
title: ICorProfilerFunctionControl::SetILFunctionBody-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 2c33f0f7-75b2-4c19-b2c7-c94b54997576
topic_type:
- apiref
ms.openlocfilehash: a6b24fd59a183a4a59b117663772417d55cc67db
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503138"
---
# <a name="icorprofilerfunctioncontrolsetilfunctionbody-method"></a><span data-ttu-id="82cf1-102">ICorProfilerFunctionControl::SetILFunctionBody-Methode</span><span class="sxs-lookup"><span data-stu-id="82cf1-102">ICorProfilerFunctionControl::SetILFunctionBody Method</span></span>
<span data-ttu-id="82cf1-103">Ersetzt den CIL-Text (Common Intermediate Language) der Methode.</span><span class="sxs-lookup"><span data-stu-id="82cf1-103">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82cf1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="82cf1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in]  ULONG   cbNewILMethodHeader,  
    [in, size_is(cbNewILMethodHeader)] LPCBYTE pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82cf1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="82cf1-105">Parameters</span></span>  
 `cbNewILMethodHeader`  
 <span data-ttu-id="82cf1-106">[in] Die Gesamtgröße der neuen CIL, einschließlich des Headers und aller Strukturen, die nach dem Text folgen.</span><span class="sxs-lookup"><span data-stu-id="82cf1-106">[in] The total size of the new CIL, including the header and any structures that come after the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="82cf1-107">[in] Ein Zeiger auf den neuen CIL-Header.</span><span class="sxs-lookup"><span data-stu-id="82cf1-107">[in] A pointer to the new CIL header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82cf1-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="82cf1-108">Return Value</span></span>  
 <span data-ttu-id="82cf1-109">Diese Methode gibt die folgenden spezifischen HRESULTs zurück.</span><span class="sxs-lookup"><span data-stu-id="82cf1-109">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="82cf1-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="82cf1-110">HRESULT</span></span>|<span data-ttu-id="82cf1-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="82cf1-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="82cf1-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="82cf1-112">S_OK</span></span>|<span data-ttu-id="82cf1-113">Die Ersetzung war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="82cf1-113">The replacement was successful.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82cf1-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="82cf1-114">Remarks</span></span>  
 <span data-ttu-id="82cf1-115">Anders als bei der [ICorProfilerInfo:: abtilfunctionbody](icorprofilerinfo-setilfunctionbody-method.md) -Methode verwaltet die- `SetILFunctionBody` Methode den für den neuen cil-Text benötigten Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="82cf1-115">Unlike the [ICorProfilerInfo::SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) method, the `SetILFunctionBody` method manages the memory required for the new CIL body.</span></span> <span data-ttu-id="82cf1-116">Dies bedeutet, dass der vom Profiler bereitgestellte cil-Text nicht mithilfe der [IMethodMalloc](imethodmalloc-interface.md) -Schnittstelle zugeordnet oder innerhalb eines bestimmten Bereichs zugeordnet werden muss.</span><span class="sxs-lookup"><span data-stu-id="82cf1-116">This means that the CIL body provided by the profiler does not have to be allocated by using the [IMethodMalloc](imethodmalloc-interface.md) interface or allocated within a particular range.</span></span> <span data-ttu-id="82cf1-117">Er kann auf jedem Heap zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="82cf1-117">It can be allocated on any heap.</span></span> <span data-ttu-id="82cf1-118">Der Profiler kann den für seinen cil-Text verwendeten Arbeitsspeicher freigeben, nachdem zurückgegeben wurde `SetILFunctionBody` .</span><span class="sxs-lookup"><span data-stu-id="82cf1-118">The profiler can free the memory used for its CIL body after `SetILFunctionBody` returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82cf1-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="82cf1-119">Requirements</span></span>  
 <span data-ttu-id="82cf1-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82cf1-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82cf1-121">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="82cf1-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="82cf1-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82cf1-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82cf1-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82cf1-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82cf1-124">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="82cf1-124">See also</span></span>

- [<span data-ttu-id="82cf1-125">ICorProfilerFunctionControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="82cf1-125">ICorProfilerFunctionControl Interface</span></span>](icorprofilerfunctioncontrol-interface.md)
