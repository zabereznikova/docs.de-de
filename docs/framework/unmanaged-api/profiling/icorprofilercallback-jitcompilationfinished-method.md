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
ms.openlocfilehash: f1cfef464569b577923fbb16624c99358998d29c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866246"
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a><span data-ttu-id="fdffe-102">ICorProfilerCallback::JITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="fdffe-102">ICorProfilerCallback::JITCompilationFinished Method</span></span>
<span data-ttu-id="fdffe-103">Benachrichtigt den Profiler, dass der JIT-Compiler (Just-in-Time) die Kompilierung einer Funktion abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="fdffe-103">Notifies the profiler that the just-in-time (JIT) compiler has finished compiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdffe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fdffe-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fdffe-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="fdffe-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="fdffe-106">\[in] die ID der Funktion, die kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="fdffe-106">\[in] The ID of the function that was compiled.</span></span>

- `hrStatus`

  <span data-ttu-id="fdffe-107">\[in] ein Wert, der angibt, ob die Kompilierung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="fdffe-107">\[in] A value indicating whether compilation was successful.</span></span>

- `fIsSafeToBlock`

  <span data-ttu-id="fdffe-108">\[in] ein Wert, der dem Profiler angibt, ob die Blockierung den Lauf Zeitvorgang beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="fdffe-108">\[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="fdffe-109">Der Wert ist `true`, wenn eine Blockierung bewirkt, dass die Laufzeit darauf wartet, dass der aufrufenden Thread von diesem Rückruf zurückgegeben wird. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="fdffe-109">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>

  <span data-ttu-id="fdffe-110">Obwohl der Wert `true` die Laufzeit nicht beeinträchtigt, kann er die Profil Erstellungs Ergebnisse verzerren.</span><span class="sxs-lookup"><span data-stu-id="fdffe-110">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>

## <a name="requirements"></a><span data-ttu-id="fdffe-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fdffe-111">Requirements</span></span>  
 <span data-ttu-id="fdffe-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdffe-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdffe-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fdffe-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fdffe-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fdffe-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fdffe-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdffe-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdffe-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fdffe-116">See also</span></span>

- [<span data-ttu-id="fdffe-117">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fdffe-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="fdffe-118">JITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="fdffe-118">JITCompilationStarted Method</span></span>](icorprofilercallback-jitcompilationstarted-method.md)
