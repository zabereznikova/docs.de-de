---
title: 'ICorProfilerInfo10:: requestrejitwithinliners'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.RequestReJITWithInliners
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 00bfc9fc21ed39226fd21c4096305c254d73ee11
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69665728"
---
# <a name="icorprofilerinfo10requestrejitwithinliners-method"></a><span data-ttu-id="11bae-102">ICorProfilerInfo10:: requestrejitwithinliners-Methode</span><span class="sxs-lookup"><span data-stu-id="11bae-102">ICorProfilerInfo10::RequestReJITWithInliners Method</span></span>

<span data-ttu-id="11bae-103">Rejits die angeforderten Methoden sowie alle inlinder angeforderten Methoden.</span><span class="sxs-lookup"><span data-stu-id="11bae-103">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>

## <a name="syntax"></a><span data-ttu-id="11bae-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="11bae-104">Syntax</span></span>

```cpp
HRESULT RequestReJITWithInliners( [in]                       DWORD       dwRejitFlags,
                                  [in]                       ULONG       cFunctions,
                                  [in, size_is(cFunctions)]  ModuleID    moduleIds[],
                                  [in, size_is(cFunctions)]  mdMethodDef methodIds[]);
```

#### <a name="parameters"></a><span data-ttu-id="11bae-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="11bae-105">Parameters</span></span>

`dwRejitFlags` \
<span data-ttu-id="11bae-106">in Eine Bitmaske von [COR_PRF_REJIT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-rejit-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="11bae-106">[in] A bitmask of [COR_PRF_REJIT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-rejit-flags-enumeration.md).</span></span>

`cFunctions` \
<span data-ttu-id="11bae-107">[in] Die Anzahl der neu zu kompilierenden Funktionen.</span><span class="sxs-lookup"><span data-stu-id="11bae-107">[in] The number of functions to recompile.</span></span>

`moduleIds` \
<span data-ttu-id="11bae-108">[in] Gibt den `moduleId`-Teil der (`module`, `methodDef`)-Paare an, mit denen die neu zu kompilierenden Funktionen identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="11bae-108">[in] Specifies the `moduleId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>

`methodIds` \
<span data-ttu-id="11bae-109">[in] Gibt den `methodId`-Teil der (`module`, `methodDef`)-Paare an, mit denen die neu zu kompilierenden Funktionen identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="11bae-109">[in] Specifies the `methodId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>

## <a name="remarks"></a><span data-ttu-id="11bae-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="11bae-110">Remarks</span></span>

<span data-ttu-id="11bae-111">[Requestrejit](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md) führt keine Nachverfolgung von Inline Methoden aus.</span><span class="sxs-lookup"><span data-stu-id="11bae-111">[RequestReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md) does not do any tracking of inlined methods.</span></span> <span data-ttu-id="11bae-112">Es wurde erwartet, dass der Profiler Inlining blockiert oder Inline nachverfolgt und `RequestReJIT` für alle Inlinedaten aufruft, um sicherzustellen, dass jede Instanz einer Inline Methode erneut generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="11bae-112">The profiler was expected to either block inlining or track inlining and call `RequestReJIT` for all inliners to make sure every instance of an inlined method was ReJITted.</span></span> <span data-ttu-id="11bae-113">Dies stellt ein Problem mit ReJIT beim Anfügen dar, da der Profiler nicht zum Überwachen des Inlining vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="11bae-113">This poses a problem with ReJIT on attach, since the profiler is not present to monitor inlining.</span></span> <span data-ttu-id="11bae-114">Diese Methode kann aufgerufen werden, um sicherzustellen, dass auch der vollständige Satz von Inliners erneut generiert wird.</span><span class="sxs-lookup"><span data-stu-id="11bae-114">This method can be called to guarantee that the full set of inliners will be ReJITted as well.</span></span>

## <a name="requirements"></a><span data-ttu-id="11bae-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="11bae-115">Requirements</span></span>

<span data-ttu-id="11bae-116">**Formen** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="11bae-116">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>

<span data-ttu-id="11bae-117">**Header:** Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="11bae-117">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="11bae-118">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11bae-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="11bae-119">**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11bae-119">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="11bae-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11bae-120">See also</span></span>

- [<span data-ttu-id="11bae-121">ICorProfilerInfo10-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="11bae-121">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
