---
title: StackSnapshotCallback-Funktion
ms.date: 03/30/2017
api_name:
- StackSnapshotCallback
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- StackSnapshotCallback
helpviewer_keywords:
- StackSnapshotCallback function [.NET Framework profiling]
ms.assetid: d0f235b2-91fe-4f82-b7d5-e5c64186eea8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5e73afa7ef33e12d6bc658c944c79ce1bc4f94f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572414"
---
# <a name="stacksnapshotcallback-function"></a><span data-ttu-id="6fbc1-102">StackSnapshotCallback-Funktion</span><span class="sxs-lookup"><span data-stu-id="6fbc1-102">StackSnapshotCallback Function</span></span>
<span data-ttu-id="6fbc1-103">Stellt Informationen über jeden verwalteten Frame und die Ausführung von nicht verwalteten Frames im Stapel während eines Stackwalks, der von initiiert wird der Profiler die [ICorProfilerInfo2:: DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="6fbc1-103">Provides the profiler with information about each managed frame and each run of unmanaged frames on the stack during a stack walk, which is initiated by the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fbc1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6fbc1-104">Syntax</span></span>  
  
```  
HRESULT __stdcall StackSnapshotCallback (  
    [in] FunctionID funcId,  
    [in] UINT_PTR ip,  
    [in] COR_PRF_FRAME_INFO frameInfo,  
    [in] ULONG32 contextSize,  
    [in] BYTE context[],  
    [in] void *clientData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6fbc1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6fbc1-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="6fbc1-106">[in] Dieser Wert 0 (null) ist, ist dieser Rückruf für eine Ausführung von nicht verwalteten Frames; Andernfalls ist der Bezeichner einer verwalteten Funktion aus, und dieser Rückruf ist für einen verwalteten Frame.</span><span class="sxs-lookup"><span data-stu-id="6fbc1-106">[in] If this value is zero, this callback is for a run of unmanaged frames; otherwise, it is the identifier of a managed function and this callback is for a managed frame.</span></span>  
  
 `ip`  
 <span data-ttu-id="6fbc1-107">[in] Der Wert des Anweisungszeigers systemeigenem Code im Frame.</span><span class="sxs-lookup"><span data-stu-id="6fbc1-107">[in] The value of the native code instruction pointer in the frame.</span></span>  
  
 `frameInfo`  
 <span data-ttu-id="6fbc1-108">[in] Ein `COR_PRF_FRAME_INFO` -Wert, der Informationen über den Stapelrahmen verweist.</span><span class="sxs-lookup"><span data-stu-id="6fbc1-108">[in] A `COR_PRF_FRAME_INFO` value that references information about the stack frame.</span></span> <span data-ttu-id="6fbc1-109">Dieser Wert ist nur während dieses Rückrufs für die Verwendung gültig.</span><span class="sxs-lookup"><span data-stu-id="6fbc1-109">This value is valid for use only during this callback.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="6fbc1-110">[in] Die Größe des der `CONTEXT` -Struktur, die verweist die `context` Parameter.</span><span class="sxs-lookup"><span data-stu-id="6fbc1-110">[in] The size of the `CONTEXT` structure, which is referenced by the `context` parameter.</span></span>  
  
 `context`  
 <span data-ttu-id="6fbc1-111">[in] Ein Zeiger auf eine Win32- `CONTEXT` -Struktur, die den Zustand der CPU für diesen Frame darstellt.</span><span class="sxs-lookup"><span data-stu-id="6fbc1-111">[in] A pointer to a Win32 `CONTEXT` structure that represents the state of the CPU for this frame.</span></span>  
  
 <span data-ttu-id="6fbc1-112">Die `context` Parameter ist nur gültig, wenn das Flag COR_PRF_SNAPSHOT_CONTEXT übergebene `ICorProfilerInfo2::DoStackSnapshot`.</span><span class="sxs-lookup"><span data-stu-id="6fbc1-112">The `context` parameter is valid only if the COR_PRF_SNAPSHOT_CONTEXT flag was passed in `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
 `clientData`  
 <span data-ttu-id="6fbc1-113">[in] Ein Zeiger auf die Clientdaten, das direkt vom übergeben wird `ICorProfilerInfo2::DoStackSnapshot`.</span><span class="sxs-lookup"><span data-stu-id="6fbc1-113">[in] A pointer to the client data, which is passed straight through from `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6fbc1-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6fbc1-114">Remarks</span></span>  
 <span data-ttu-id="6fbc1-115">Die `StackSnapshotCallback` Funktion wird von der Profilerwriter implementiert.</span><span class="sxs-lookup"><span data-stu-id="6fbc1-115">The `StackSnapshotCallback` function is implemented by the profiler writer.</span></span> <span data-ttu-id="6fbc1-116">Sie müssen die Komplexität der Arbeit in begrenzen `StackSnapshotCallback`.</span><span class="sxs-lookup"><span data-stu-id="6fbc1-116">You must limit the complexity of work done in `StackSnapshotCallback`.</span></span> <span data-ttu-id="6fbc1-117">Beispielsweise wird bei Verwendung `ICorProfilerInfo2::DoStackSnapshot` auf asynchrone Weise, der Zielthread belegt sperren.</span><span class="sxs-lookup"><span data-stu-id="6fbc1-117">For example, when using `ICorProfilerInfo2::DoStackSnapshot` in an asynchronous manner, the target thread may be holding locks.</span></span> <span data-ttu-id="6fbc1-118">Wenn code in `StackSnapshotCallback` erfordert die Sperren, kann ein Deadlock zur Folge haben.</span><span class="sxs-lookup"><span data-stu-id="6fbc1-118">If code within `StackSnapshotCallback` requires the same locks, a deadlock could ensue.</span></span>  
  
 <span data-ttu-id="6fbc1-119">Die `ICorProfilerInfo2::DoStackSnapshot` Methodenaufrufe der `StackSnapshotCallback` Funktion einmal pro verwalteten Frame oder einmal pro Ausführung nicht verwalteter Frames.</span><span class="sxs-lookup"><span data-stu-id="6fbc1-119">The `ICorProfilerInfo2::DoStackSnapshot` method calls the `StackSnapshotCallback` function once per managed frame or once per run of unmanaged frames.</span></span> <span data-ttu-id="6fbc1-120">Wenn `StackSnapshotCallback` wird aufgerufen, für eine Ausführung von nicht verwalteten Frames, kann der Profiler den Registerkontext verwenden (Verweis durch die `context` Parameter), einen eigenen nicht verwalteten Stapeldurchlauf durchführen.</span><span class="sxs-lookup"><span data-stu-id="6fbc1-120">If `StackSnapshotCallback` is called for a run of unmanaged frames, the profiler may use the register context (referenced by the `context` parameter) to perform its own unmanaged stack walk.</span></span> <span data-ttu-id="6fbc1-121">In diesem Fall die Win32 `CONTEXT` Struktur darstellt, die CPU-Status für den zuletzt abgelegte Frame in der Ausführung von nicht verwalteten Frames.</span><span class="sxs-lookup"><span data-stu-id="6fbc1-121">In this case, the Win32 `CONTEXT` structure represents the CPU state for the most recently pushed frame within the run of unmanaged frames.</span></span> <span data-ttu-id="6fbc1-122">Obwohl die Win32 `CONTEXT` Struktur enthält Werte für alle Register, sollten Sie eine verlassen nur auf die Werte der Stapelzeigerregister, Framezeigerregister, Anweisungszeigerregister und die permanenten (der beibehalten wird) Ganzzahl-Register.</span><span class="sxs-lookup"><span data-stu-id="6fbc1-122">Although the Win32 `CONTEXT` structure includes values for all registers, you should rely only on the values of the stack pointer register, frame pointer register, instruction pointer register, and the nonvolatile (that is, preserved) integer registers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fbc1-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6fbc1-123">Requirements</span></span>  
 <span data-ttu-id="6fbc1-124">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fbc1-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fbc1-125">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="6fbc1-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="6fbc1-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6fbc1-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6fbc1-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fbc1-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fbc1-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6fbc1-128">See also</span></span>
- [<span data-ttu-id="6fbc1-129">DoStackSnapshot-Methode</span><span class="sxs-lookup"><span data-stu-id="6fbc1-129">DoStackSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="6fbc1-130">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="6fbc1-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
