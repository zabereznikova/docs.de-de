---
title: ICorProfilerCallback::JITCompilationFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationFinished
helpviewer_keywords:
- JITCompilationFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationFinished method [.NET Framework profiling]
ms.assetid: 8dcd7537-d0c6-498c-8a56-2c060310ef65
topic_type:
- apiref
ms.openlocfilehash: 98e81d2d02a9495b678d49fb916f99068dd604f8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725533"
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a><span data-ttu-id="39544-102">ICorProfilerCallback::JITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="39544-102">ICorProfilerCallback::JITCompilationFinished Method</span></span>

<span data-ttu-id="39544-103">Benachrichtigt den Profiler, dass der JIT-Compiler (Just-in-Time) die Kompilierung einer Funktion abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="39544-103">Notifies the profiler that the just-in-time (JIT) compiler has finished compiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39544-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="39544-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39544-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="39544-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="39544-106">\[in] die ID der Funktion, die kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="39544-106">\[in] The ID of the function that was compiled.</span></span>

- `hrStatus`

  <span data-ttu-id="39544-107">\[in] ein Wert, der angibt, ob die Kompilierung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="39544-107">\[in] A value indicating whether compilation was successful.</span></span>

- `fIsSafeToBlock`

  <span data-ttu-id="39544-108">\[in] ein Wert, der angibt, ob die Blockierung den Lauf Zeitvorgang beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="39544-108">\[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="39544-109">Der Wert ist `true` , wenn die-Sperre bewirken kann, dass die Laufzeit auf die Rückgabe des aufrufenden Threads von diesem Rückruf wartet, andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="39544-109">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>

  <span data-ttu-id="39544-110">Obwohl der Wert für `true` die Laufzeit nicht beeinträchtigt wird, kann er die Profil Erstellungs Ergebnisse verzerren.</span><span class="sxs-lookup"><span data-stu-id="39544-110">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>

## <a name="requirements"></a><span data-ttu-id="39544-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="39544-111">Requirements</span></span>  

 <span data-ttu-id="39544-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39544-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39544-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="39544-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="39544-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39544-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39544-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39544-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39544-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="39544-116">See also</span></span>

- [<span data-ttu-id="39544-117">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="39544-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="39544-118">JITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="39544-118">JITCompilationStarted Method</span></span>](icorprofilercallback-jitcompilationstarted-method.md)
