---
title: ICorProfilerInfo4::GetILToNativeMapping2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetILToNativeMapping2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetILToNativeMapping2
helpviewer_keywords:
- ICorProfilerInfo4::GetILToNativeMapping2 method [.NET Framework profiling]
- GetILToNativeMapping2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 756c1c25-08a7-4060-9798-dbeaa2f3bee5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bd3ccbe2b6b33e873bdb647987b38aeef74c1b2c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552488"
---
# <a name="icorprofilerinfo4getiltonativemapping2-method"></a><span data-ttu-id="41945-102">ICorProfilerInfo4::GetILToNativeMapping2-Methode</span><span class="sxs-lookup"><span data-stu-id="41945-102">ICorProfilerInfo4::GetILToNativeMapping2 Method</span></span>
<span data-ttu-id="41945-103">Ruft eine Zuordnung zwischen MSIL-Offsets (Microsoft Intermediate Language) und systemeigenen Offsets für den Code ab, der in der erneut JIT-kompilierten Version der angegebenen Funktion enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="41945-103">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41945-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="41945-104">Syntax</span></span>  
  
```  
HRESULT GetILToNativeMapping(  
    [in] FunctionID functionId,  
    [in] ReJITID reJitId,  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="41945-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="41945-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="41945-106">[in] Die ID der Funktion, die den Code enthält.</span><span class="sxs-lookup"><span data-stu-id="41945-106">[in] The ID of the function that contains the code.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="41945-107">[in] Die Identität der erneut JIT-kompilierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="41945-107">[in] The identity of the JIT-recompiled function.</span></span> <span data-ttu-id="41945-108">Die Identität muss in [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] null sein.</span><span class="sxs-lookup"><span data-stu-id="41945-108">The identity must be zero in the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span></span>  
  
 `cMap`  
 <span data-ttu-id="41945-109">[in] Die maximale Größe des `map`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="41945-109">[in] The maximum size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="41945-110">[out] Die Gesamtanzahl verfügbarer COR_DEBUG_IL_TO_NATIVE_MAP-Strukturen.</span><span class="sxs-lookup"><span data-stu-id="41945-110">[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>  
  
 `map`  
 <span data-ttu-id="41945-111">[out] Ein Array von `COR_DEBUG_IL_TO_NATIVE_MAP`-Strukturen, die jeweils die Offsets angeben.</span><span class="sxs-lookup"><span data-stu-id="41945-111">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which specifies the offsets.</span></span> <span data-ttu-id="41945-112">Nach Rückgabe der `GetILToNativeMapping2`-Methode enthält `map` einige oder alle `COR_DEBUG_IL_TO_NATIVE_MAP`-Strukturen.</span><span class="sxs-lookup"><span data-stu-id="41945-112">After the `GetILToNativeMapping2` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41945-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="41945-113">Remarks</span></span>  
 <span data-ttu-id="41945-114">`GetILToNativeMapping2` ähnelt der [ICorProfilerInfo:: GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) -Methode, außer dass es den Profiler, geben Sie die ID der erneut kompilierten Funktion in Zukunft kann frei.</span><span class="sxs-lookup"><span data-stu-id="41945-114">`GetILToNativeMapping2` is similar to the [ICorProfilerInfo::GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) method, except that it will allow the profiler to specify the ID of the recompiled function in future releases.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="41945-115">Die [icorprofilerfunctioncontrol:: SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md) Methode ist nicht implementiert, der [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], sodass die Funktionen, die erneut JIT-kompilierten wurden eine IL-Code und systemeigenem Zuordnung aufweisen können, die von unterscheidet die ursprünglich kompilierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="41945-115">The [ICorProfilerFunctionControl::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md) method is not implemented in the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], so functions that have been JIT-recompiled cannot have an IL-to-native mapping that differs from the originally compiled function.</span></span> <span data-ttu-id="41945-116">Daher kann `GetILToNativeMapping2` nicht mit einer erneut JIT-kompilierten ID ungleich null in [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="41945-116">As such, `GetILToNativeMapping2` cannot be called with a nonzero JIT-recompiled ID in the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span></span>  
  
 <span data-ttu-id="41945-117">Die `GetILToNativeMapping2`-Methode gibt ein Array von `COR_DEBUG_IL_TO_NATIVE_MAP`-Strukturen zurück.</span><span class="sxs-lookup"><span data-stu-id="41945-117">The `GetILToNativeMapping2` method returns an array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="41945-118">Um zu beschreiben, dass bestimmte Bereiche systemeigener Anweisungen besonderen Codebereichen (beispielsweise dem Prolog) entsprechen, haben ein Eintrag im Array dessen `ilOffset` Feld festgelegt werden, auf den Wert der [CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) -Enumeration.</span><span class="sxs-lookup"><span data-stu-id="41945-118">To convey that certain ranges of native instructions correspond to special regions of code (for example, the prolog), an entry in the array can have its `ilOffset` field set to a value of the [CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="41945-119">Nachdem `GetILToNativeMapping2` zurückgegeben wurde, müssen Sie sicherstellen, dass der `map`-Puffer groß genug war, um alle `COR_DEBUG_IL_TO_NATIVE_MAP`-Strukturen aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="41945-119">After `GetILToNativeMapping2` returns, you must verify that the `map` buffer was large enough to contain all the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="41945-120">Dazu vergleichen Sie den Wert von `cMap` mit dem Wert des `pcMap`-Parameters.</span><span class="sxs-lookup"><span data-stu-id="41945-120">To do this, compare the value of `cMap` with the value of the `pcMap` parameter.</span></span> <span data-ttu-id="41945-121">Wenn der `pcMap`-Wert nach Multiplikation mit der Größe einer `COR_DEBUG_IL_TO_NATIVE_MAP`-Struktur größer als `cMap` ist, weisen Sie einen größeren `map`-Puffer zu, aktualisieren Sie `cMap` mit der neuen Größe, und rufen Sie `GetILToNativeMapping2` erneut auf.</span><span class="sxs-lookup"><span data-stu-id="41945-121">If the `pcMap` value, when it is multiplied by the size of a `COR_DEBUG_IL_TO_NATIVE_MAP` structure, is larger than `cMap`, allocate a larger `map` buffer, update `cMap` with the new, larger size, and call `GetILToNativeMapping2` again.</span></span>  
  
 <span data-ttu-id="41945-122">Alternativ können Sie zuerst `GetILToNativeMapping2` mit einem `map`-Puffer der Länge 0 (null) aufrufen, um die richtige Puffergröße zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="41945-122">Alternatively, you can first call `GetILToNativeMapping2` with a zero-length `map` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="41945-123">Sie können die Puffergröße dann auf den Wert festlegen, der von `pcMap` zurückgegeben wurde, und `GetILToNativeMapping2` erneut aufrufen.</span><span class="sxs-lookup"><span data-stu-id="41945-123">You can then set the buffer size to the value returned in `pcMap` and call `GetILToNativeMapping2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41945-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="41945-124">Requirements</span></span>  
 <span data-ttu-id="41945-125">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41945-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41945-126">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="41945-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="41945-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41945-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41945-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41945-128">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41945-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41945-129">See also</span></span>
- [<span data-ttu-id="41945-130">GetILToNativeMapping-Methode</span><span class="sxs-lookup"><span data-stu-id="41945-130">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="41945-131">ICorProfilerInfo4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="41945-131">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="41945-132">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="41945-132">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="41945-133">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="41945-133">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
