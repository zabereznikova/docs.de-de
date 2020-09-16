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
ms.openlocfilehash: e3d5a09730cb8e477bd506749017a403acff1696
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540557"
---
# <a name="icorprofilerinfo10requestrejitwithinliners-method"></a><span data-ttu-id="c95cc-102">ICorProfilerInfo10:: requestrejitwithinliners-Methode</span><span class="sxs-lookup"><span data-stu-id="c95cc-102">ICorProfilerInfo10::RequestReJITWithInliners Method</span></span>

<span data-ttu-id="c95cc-103">Rejits die angeforderten Methoden sowie alle inlinder angeforderten Methoden.</span><span class="sxs-lookup"><span data-stu-id="c95cc-103">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>

## <a name="syntax"></a><span data-ttu-id="c95cc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c95cc-104">Syntax</span></span>

```cpp
HRESULT RequestReJITWithInliners( [in]                       DWORD       dwRejitFlags,
                                  [in]                       ULONG       cFunctions,
                                  [in, size_is(cFunctions)]  ModuleID    moduleIds[],
                                  [in, size_is(cFunctions)]  mdMethodDef methodIds[]);
```

## <a name="parameters"></a><span data-ttu-id="c95cc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c95cc-105">Parameters</span></span>

- `dwRejitFlags`

  <span data-ttu-id="c95cc-106">\[in] eine Bitmaske von [COR_PRF_REJIT_FLAGS](cor-prf-rejit-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="c95cc-106">\[in] A bitmask of [COR_PRF_REJIT_FLAGS](cor-prf-rejit-flags-enumeration.md).</span></span>

- `cFunctions`

  <span data-ttu-id="c95cc-107">\[in] die Anzahl der neu zu kompilierenden Funktionen.</span><span class="sxs-lookup"><span data-stu-id="c95cc-107">\[in] The number of functions to recompile.</span></span>

- `moduleIds`

  <span data-ttu-id="c95cc-108">\[in] gibt den- `moduleId` Teil der ( `module` , `methodDef` )-Paare an, mit denen die neu zu kompilierenden Funktionen identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="c95cc-108">\[in] Specifies the `moduleId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>

- `methodIds`

  <span data-ttu-id="c95cc-109">\[in] gibt den- `methodId` Teil der ( `module` , `methodDef` )-Paare an, mit denen die neu zu kompilierenden Funktionen identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="c95cc-109">\[in] Specifies the `methodId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>

## <a name="remarks"></a><span data-ttu-id="c95cc-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c95cc-110">Remarks</span></span>

<span data-ttu-id="c95cc-111">[Requestrejit](icorprofilerinfo4-requestrejit-method.md) führt keine Nachverfolgung von Inline Methoden aus.</span><span class="sxs-lookup"><span data-stu-id="c95cc-111">[RequestReJIT](icorprofilerinfo4-requestrejit-method.md) does not do any tracking of inlined methods.</span></span> <span data-ttu-id="c95cc-112">Es wurde erwartet, dass der Profiler Inlining blockiert oder Inline nachverfolgt und `RequestReJIT` für alle Inlinedaten aufruft, um sicherzustellen, dass jede Instanz einer Inline Methode erneut generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c95cc-112">The profiler was expected to either block inlining or track inlining and call `RequestReJIT` for all inliners to make sure every instance of an inlined method was ReJITted.</span></span> <span data-ttu-id="c95cc-113">Dies stellt ein Problem mit ReJIT beim Anfügen dar, da der Profiler nicht zum Überwachen des Inlining vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c95cc-113">This poses a problem with ReJIT on attach, since the profiler is not present to monitor inlining.</span></span> <span data-ttu-id="c95cc-114">Diese Methode kann aufgerufen werden, um sicherzustellen, dass auch der vollständige Satz von Inliners erneut generiert wird.</span><span class="sxs-lookup"><span data-stu-id="c95cc-114">This method can be called to guarantee that the full set of inliners will be ReJITted as well.</span></span>

## <a name="requirements"></a><span data-ttu-id="c95cc-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c95cc-115">Requirements</span></span>

<span data-ttu-id="c95cc-116">**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="c95cc-116">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="c95cc-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c95cc-117">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="c95cc-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c95cc-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="c95cc-119">**.NET-Versionen:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c95cc-119">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c95cc-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c95cc-120">See also</span></span>

- [<span data-ttu-id="c95cc-121">ICorProfilerInfo10-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c95cc-121">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
