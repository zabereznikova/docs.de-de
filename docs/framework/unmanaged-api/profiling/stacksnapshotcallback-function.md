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
ms.openlocfilehash: 2d6ca18ce48f69d8c94b465efac2b9fe0e10f070
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685304"
---
# <a name="stacksnapshotcallback-function"></a><span data-ttu-id="263bb-102">StackSnapshotCallback-Funktion</span><span class="sxs-lookup"><span data-stu-id="263bb-102">StackSnapshotCallback Function</span></span>

<span data-ttu-id="263bb-103">Stellt dem Profiler Informationen über jeden verwalteten Frame und jede ausführen nicht verwalteter Frames auf dem Stapel während eines Stackwalk bereit, der von der [ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) -Methode initiiert wird.</span><span class="sxs-lookup"><span data-stu-id="263bb-103">Provides the profiler with information about each managed frame and each run of unmanaged frames on the stack during a stack walk, which is initiated by the [ICorProfilerInfo2::DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="263bb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="263bb-104">Syntax</span></span>  
  
```cpp  
HRESULT __stdcall StackSnapshotCallback (  
    [in] FunctionID funcId,  
    [in] UINT_PTR ip,  
    [in] COR_PRF_FRAME_INFO frameInfo,  
    [in] ULONG32 contextSize,  
    [in] BYTE context[],  
    [in] void *clientData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="263bb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="263bb-105">Parameters</span></span>  

 `funcId`  
 <span data-ttu-id="263bb-106">in Wenn dieser Wert 0 (null) ist, ist dieser Rückruf für die Durchführung nicht verwalteter Frames vorgesehen. andernfalls handelt es sich um den Bezeichner einer verwalteten Funktion, und dieser Rückruf gilt für einen verwalteten Frame.</span><span class="sxs-lookup"><span data-stu-id="263bb-106">[in] If this value is zero, this callback is for a run of unmanaged frames; otherwise, it is the identifier of a managed function and this callback is for a managed frame.</span></span>  
  
 `ip`  
 <span data-ttu-id="263bb-107">in Der Wert des systemeigenen Code Anweisungs Zeigers im Frame.</span><span class="sxs-lookup"><span data-stu-id="263bb-107">[in] The value of the native code instruction pointer in the frame.</span></span>  
  
 `frameInfo`  
 <span data-ttu-id="263bb-108">in Ein- `COR_PRF_FRAME_INFO` Wert, der auf Informationen über den Stapel Rahmen verweist.</span><span class="sxs-lookup"><span data-stu-id="263bb-108">[in] A `COR_PRF_FRAME_INFO` value that references information about the stack frame.</span></span> <span data-ttu-id="263bb-109">Dieser Wert kann nur während dieses Rückrufs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="263bb-109">This value is valid for use only during this callback.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="263bb-110">in Die Größe der- `CONTEXT` Struktur, auf die vom-Parameter verwiesen wird `context` .</span><span class="sxs-lookup"><span data-stu-id="263bb-110">[in] The size of the `CONTEXT` structure, which is referenced by the `context` parameter.</span></span>  
  
 `context`  
 <span data-ttu-id="263bb-111">in Ein Zeiger auf eine Win32-- `CONTEXT` Struktur, die den Zustand der CPU für diesen Frame darstellt.</span><span class="sxs-lookup"><span data-stu-id="263bb-111">[in] A pointer to a Win32 `CONTEXT` structure that represents the state of the CPU for this frame.</span></span>  
  
 <span data-ttu-id="263bb-112">Der- `context` Parameter ist nur gültig, wenn das COR_PRF_SNAPSHOT_CONTEXT-Flag übergeben wurde `ICorProfilerInfo2::DoStackSnapshot` .</span><span class="sxs-lookup"><span data-stu-id="263bb-112">The `context` parameter is valid only if the COR_PRF_SNAPSHOT_CONTEXT flag was passed in `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
 `clientData`  
 <span data-ttu-id="263bb-113">in Ein Zeiger auf die Client Daten, der direkt von der übermittelt wird `ICorProfilerInfo2::DoStackSnapshot` .</span><span class="sxs-lookup"><span data-stu-id="263bb-113">[in] A pointer to the client data, which is passed straight through from `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="263bb-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="263bb-114">Remarks</span></span>  

 <span data-ttu-id="263bb-115">Die- `StackSnapshotCallback` Funktion wird vom Profiler-Writer implementiert.</span><span class="sxs-lookup"><span data-stu-id="263bb-115">The `StackSnapshotCallback` function is implemented by the profiler writer.</span></span> <span data-ttu-id="263bb-116">Sie müssen die Komplexität der in durchgeführten Arbeit einschränken `StackSnapshotCallback` .</span><span class="sxs-lookup"><span data-stu-id="263bb-116">You must limit the complexity of work done in `StackSnapshotCallback`.</span></span> <span data-ttu-id="263bb-117">Wenn Sie beispielsweise `ICorProfilerInfo2::DoStackSnapshot` asynchron verwenden, kann der Zielthread Sperren aufrechterhalten.</span><span class="sxs-lookup"><span data-stu-id="263bb-117">For example, when using `ICorProfilerInfo2::DoStackSnapshot` in an asynchronous manner, the target thread may be holding locks.</span></span> <span data-ttu-id="263bb-118">Wenn Code in `StackSnapshotCallback` die gleichen Sperren erfordert, könnte ein Deadlock entstehen.</span><span class="sxs-lookup"><span data-stu-id="263bb-118">If code within `StackSnapshotCallback` requires the same locks, a deadlock could ensue.</span></span>  
  
 <span data-ttu-id="263bb-119">Die- `ICorProfilerInfo2::DoStackSnapshot` Methode ruft die- `StackSnapshotCallback` Funktion einmal pro verwaltetem Frame oder einmal pro ausführen nicht verwalteter Frames auf.</span><span class="sxs-lookup"><span data-stu-id="263bb-119">The `ICorProfilerInfo2::DoStackSnapshot` method calls the `StackSnapshotCallback` function once per managed frame or once per run of unmanaged frames.</span></span> <span data-ttu-id="263bb-120">Wenn `StackSnapshotCallback` für eine Ausführung nicht verwalteter Frames aufgerufen wird, kann der Profiler den Registrierungs Kontext (auf den der- `context` Parameter verweist) verwenden, um einen eigenen nicht verwalteten Stackwalk auszuführen.</span><span class="sxs-lookup"><span data-stu-id="263bb-120">If `StackSnapshotCallback` is called for a run of unmanaged frames, the profiler may use the register context (referenced by the `context` parameter) to perform its own unmanaged stack walk.</span></span> <span data-ttu-id="263bb-121">In diesem Fall stellt die Win32- `CONTEXT` Struktur den CPU-Status für den zuletzt über drückten Rahmen während der Durchführung nicht verwalteter Frames dar.</span><span class="sxs-lookup"><span data-stu-id="263bb-121">In this case, the Win32 `CONTEXT` structure represents the CPU state for the most recently pushed frame within the run of unmanaged frames.</span></span> <span data-ttu-id="263bb-122">Obwohl die Win32- `CONTEXT` Struktur Werte für alle Register enthält, sollten Sie sich nur auf die Werte der Stapelzeiger Register, das Frame Zeiger Register, das Anweisungs Zeiger Register und die nicht flüchtigen (d. h. beibehaltenen) ganzzahligen Register verlassen.</span><span class="sxs-lookup"><span data-stu-id="263bb-122">Although the Win32 `CONTEXT` structure includes values for all registers, you should rely only on the values of the stack pointer register, frame pointer register, instruction pointer register, and the nonvolatile (that is, preserved) integer registers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="263bb-123">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="263bb-123">Requirements</span></span>  

 <span data-ttu-id="263bb-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="263bb-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="263bb-125">**Header:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="263bb-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="263bb-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="263bb-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="263bb-127">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="263bb-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="263bb-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="263bb-128">See also</span></span>

- [<span data-ttu-id="263bb-129">DoStackSnapshot-Methode</span><span class="sxs-lookup"><span data-stu-id="263bb-129">DoStackSnapshot Method</span></span>](icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="263bb-130">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="263bb-130">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
