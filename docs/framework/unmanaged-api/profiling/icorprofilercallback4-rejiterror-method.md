---
title: ICorProfilerCallback4::ReJITError-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITError
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITError
helpviewer_keywords:
- ReJITError method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITError method [.NET Framework profiling]
ms.assetid: d7888aa9-dfaa-420f-9f99-e06ab35ca482
topic_type:
- apiref
ms.openlocfilehash: 6ea9dee6e83870d1f2e0fdccffa53f16e6f18dba
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430108"
---
# <a name="icorprofilercallback4rejiterror-method"></a><span data-ttu-id="2e9ca-102">ICorProfilerCallback4::ReJITError-Methode</span><span class="sxs-lookup"><span data-stu-id="2e9ca-102">ICorProfilerCallback4::ReJITError Method</span></span>
<span data-ttu-id="2e9ca-103">Benachrichtigt den Profiler, dass der JIT-Compiler (Just-in-Time) einen Fehler im neukompilierungs Prozess festgestellt hat.</span><span class="sxs-lookup"><span data-stu-id="2e9ca-103">Notifies the profiler that the just-in-time (JIT) compiler encountered an error in the recompilation process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e9ca-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2e9ca-104">Syntax</span></span>  
  
```cpp  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e9ca-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2e9ca-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="2e9ca-106">in Die `ModuleID`, in der der fehlgeschlagene neukompilierungs Versuch erfolgte.</span><span class="sxs-lookup"><span data-stu-id="2e9ca-106">[in] The `ModuleID` in which the failed recompilation attempt was made.</span></span>  
  
 `methodId`  
 <span data-ttu-id="2e9ca-107">in Der `MethodDef` der Methode, für die der fehlgeschlagene neukompilierungs Versuch durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="2e9ca-107">[in] The `MethodDef` of the method on which the failed recompilation attempt was made.</span></span>  
  
 `functionId`  
 <span data-ttu-id="2e9ca-108">in Die Funktions Instanz, die erneut kompiliert oder für die Neukompilierung markiert wird.</span><span class="sxs-lookup"><span data-stu-id="2e9ca-108">[in] The function instance that is being recompiled or marked for recompilation.</span></span> <span data-ttu-id="2e9ca-109">Dieser Wert kann `NULL` sein, wenn der Fehler nicht pro Instanziierung, sondern pro Methode aufgetreten ist (z. b. wenn der Profiler ein ungültiges Metadatentoken für die neu zu kompilierende Methode angegeben hat).</span><span class="sxs-lookup"><span data-stu-id="2e9ca-109">This value may be `NULL` if the failure occurred on a per-method basis instead of a per-instantiation basis (for example, if the profiler specified an invalid metadata token for the method to be recompiled).</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="2e9ca-110">in Ein HRESULT, das die Art des Fehlers angibt.</span><span class="sxs-lookup"><span data-stu-id="2e9ca-110">[in] An HRESULT that indicates the nature of the failure.</span></span> <span data-ttu-id="2e9ca-111">Eine Liste der Werte finden Sie im Abschnitt "Status-HRESULTs".</span><span class="sxs-lookup"><span data-stu-id="2e9ca-111">See the Status HRESULTS section for a list of values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2e9ca-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2e9ca-112">Return Value</span></span>  
 <span data-ttu-id="2e9ca-113">Rückgabewerte von diesem Rückruf werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="2e9ca-113">Return values from this callback are ignored.</span></span>  
  
## <a name="status-hresults"></a><span data-ttu-id="2e9ca-114">Status HRESULTS</span><span class="sxs-lookup"><span data-stu-id="2e9ca-114">Status HRESULTS</span></span>  
  
|<span data-ttu-id="2e9ca-115">Statusarray HRESULT</span><span class="sxs-lookup"><span data-stu-id="2e9ca-115">Status array HRESULT</span></span>|<span data-ttu-id="2e9ca-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e9ca-116">Description</span></span>|  
|--------------------------|-----------------|  
|<span data-ttu-id="2e9ca-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2e9ca-117">E_INVALIDARG</span></span>|<span data-ttu-id="2e9ca-118">Die `moduleID` oder `methodDef` Token ist `NULL`.</span><span class="sxs-lookup"><span data-stu-id="2e9ca-118">The `moduleID` or `methodDef` token is `NULL`.</span></span>|  
|<span data-ttu-id="2e9ca-119">CORPROF_E_DATAINCOMPLETE</span><span class="sxs-lookup"><span data-stu-id="2e9ca-119">CORPROF_E_DATAINCOMPLETE</span></span>|<span data-ttu-id="2e9ca-120">Das Modul ist noch nicht vollständig geladen, oder es wird gerade entladen.</span><span class="sxs-lookup"><span data-stu-id="2e9ca-120">The module is not fully loaded yet, or it is in the process of being unloaded.</span></span>|  
|<span data-ttu-id="2e9ca-121">CORPROF_E_MODULE_IS_DYNAMIC</span><span class="sxs-lookup"><span data-stu-id="2e9ca-121">CORPROF_E_MODULE_IS_DYNAMIC</span></span>|<span data-ttu-id="2e9ca-122">Das angegebene Modul wurde dynamisch generiert (z. b. durch `Reflection.Emit`) und wird daher von dieser Methode nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2e9ca-122">The specified module was dynamically generated (for example, by `Reflection.Emit`), and is thus not supported by this method.</span></span>|  
|<span data-ttu-id="2e9ca-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span><span class="sxs-lookup"><span data-stu-id="2e9ca-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span></span>|<span data-ttu-id="2e9ca-124">Die-Methode wird in einer entladbaren Assembly instanziiert und kann daher nicht erneut kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="2e9ca-124">The method is instantiated into a collectible assembly, and is therefore not able to be recompiled.</span></span> <span data-ttu-id="2e9ca-125">Beachten Sie, dass Typen und Funktionen, die in einem nicht Reflektionskontext (z. b. `List<MyCollectibleStruct>`) definiert sind, in einer entladbaren Assembly instanziiert werden können.</span><span class="sxs-lookup"><span data-stu-id="2e9ca-125">Note that types and functions defined in a non-reflection context (for example, `List<MyCollectibleStruct>`) can be instantiated into a collectible assembly.</span></span>|  
|<span data-ttu-id="2e9ca-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="2e9ca-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="2e9ca-127">Die CLR hatte beim Versuch, die angegebene Methode für die JIT-Neukompilierung zu markieren, nicht genügend Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="2e9ca-127">The CLR ran out of memory while trying to mark the specified method for JIT recompilation.</span></span>|  
|<span data-ttu-id="2e9ca-128">Andere</span><span class="sxs-lookup"><span data-stu-id="2e9ca-128">Other</span></span>|<span data-ttu-id="2e9ca-129">Das Betriebssystem hat einen Fehler außerhalb der Kontrolle der CLR zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2e9ca-129">The operating system returned a failure outside the control of the CLR.</span></span> <span data-ttu-id="2e9ca-130">Wenn beispielsweise ein Systemaufrufe zum Ändern des Zugriffs Schutzes einer Arbeitsspeicher Seite fehlschlägt, wird der Fehler des Betriebssystems angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2e9ca-130">For example, if a system call to change the access protection of a page of memory fails, the operating system error is displayed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2e9ca-131">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="2e9ca-131">Requirements</span></span>  
 <span data-ttu-id="2e9ca-132">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e9ca-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e9ca-133">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2e9ca-133">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2e9ca-134">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e9ca-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e9ca-135">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e9ca-135">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e9ca-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e9ca-136">See also</span></span>

- [<span data-ttu-id="2e9ca-137">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2e9ca-137">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="2e9ca-138">ICorProfilerCallback4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2e9ca-138">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
