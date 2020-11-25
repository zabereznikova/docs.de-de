---
title: ICorProfilerInfo::GetILToNativeMapping-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILToNativeMapping
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetILToNativeMapping method [.NET Framework profiling]
ms.assetid: 6a5431ef-22fb-4e53-bac5-703986297eb1
topic_type:
- apiref
ms.openlocfilehash: 1eb9b3af4c0e77fd1548de194d064eb85b86cdce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724155"
---
# <a name="icorprofilerinfogetiltonativemapping-method"></a><span data-ttu-id="06220-102">ICorProfilerInfo::GetILToNativeMapping-Methode</span><span class="sxs-lookup"><span data-stu-id="06220-102">ICorProfilerInfo::GetILToNativeMapping Method</span></span>

<span data-ttu-id="06220-103">Ruft für den in der angegebenen Funktion enthaltenen Code eine Zuordnung von MSIL-Offsets (Microsoft Intermediate Language) zu systemeigenen Offsets ab.</span><span class="sxs-lookup"><span data-stu-id="06220-103">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06220-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="06220-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILToNativeMapping(  
    [in] FunctionID functionId,  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06220-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="06220-105">Parameters</span></span>  

 `functionId`  
 <span data-ttu-id="06220-106">[in] Die ID der Funktion, die den Code enthält.</span><span class="sxs-lookup"><span data-stu-id="06220-106">[in] The ID of the function that contains the code.</span></span>  
  
 `cMap`  
 <span data-ttu-id="06220-107">[in] Die maximale Größe des `map`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="06220-107">[in] The maximum size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="06220-108">[out] Die Gesamtanzahl verfügbarer COR_DEBUG_IL_TO_NATIVE_MAP-Strukturen.</span><span class="sxs-lookup"><span data-stu-id="06220-108">[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>  
  
 `map`  
 <span data-ttu-id="06220-109">[out] Ein Array von `COR_DEBUG_IL_TO_NATIVE_MAP`-Strukturen, die jeweils die Offsets angeben.</span><span class="sxs-lookup"><span data-stu-id="06220-109">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which specifies the offsets.</span></span> <span data-ttu-id="06220-110">Nach Rückgabe der `GetILToNativeMapping`-Methode enthält `map` einige oder alle `COR_DEBUG_IL_TO_NATIVE_MAP`-Strukturen.</span><span class="sxs-lookup"><span data-stu-id="06220-110">After the `GetILToNativeMapping` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06220-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="06220-111">Remarks</span></span>  

 <span data-ttu-id="06220-112">Die `GetILToNativeMapping`-Methode gibt ein Array von `COR_DEBUG_IL_TO_NATIVE_MAP`-Strukturen zurück.</span><span class="sxs-lookup"><span data-stu-id="06220-112">The `GetILToNativeMapping` method returns an array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="06220-113">Um zu verdeutlichen, dass bestimmte Bereiche nativer Anweisungen speziellen Codebereichen entsprechen (z. b. dem Prolog), kann für einen Eintrag im Array das `ilOffset` Feld auf einen Wert der [CorDebugIlToNativeMappingTypes](../debugging/cordebugiltonativemappingtypes-enumeration.md) -Enumeration festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="06220-113">To convey that certain ranges of native instructions correspond to special regions of code (for example, the prolog), an entry in the array can have its `ilOffset` field set to a value of the [CorDebugIlToNativeMappingTypes](../debugging/cordebugiltonativemappingtypes-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="06220-114">Nachdem `GetILToNativeMapping` ausgeführt ist, müssen Sie sich vergewissern, dass der `map`-Puffer groß genug war, um alle `COR_DEBUG_IL_TO_NATIVE_MAP`-Strukturen zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="06220-114">After `GetILToNativeMapping` returns, you must verify that the `map` buffer was large enough to contain all the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="06220-115">Vergleichen Sie hierzu den Wert von `cMap` mit dem Wert des `pcMap`-Parameters.</span><span class="sxs-lookup"><span data-stu-id="06220-115">To do this, compare the value of `cMap` with the value of the `pcMap` parameter.</span></span> <span data-ttu-id="06220-116">Wenn der `pcMap`-Wert nach Multiplikation mit der Größe einer `COR_DEBUG_IL_TO_NATIVE_MAP`-Struktur größer als `cMap` ist, weisen Sie einen größeren `map`-Puffer zu, aktualisieren Sie `cMap` mit der neuen Größe, und rufen Sie `GetILToNativeMapping` erneut auf.</span><span class="sxs-lookup"><span data-stu-id="06220-116">If the `pcMap` value, when it is multiplied by the size of a `COR_DEBUG_IL_TO_NATIVE_MAP` structure, is larger than `cMap`, allocate a larger `map` buffer, update `cMap` with the new, larger size, and call `GetILToNativeMapping` again.</span></span>  
  
 <span data-ttu-id="06220-117">Alternativ können Sie zuerst `GetILToNativeMapping` mit einem `map`-Puffer der Länge 0 (NULL) aufrufen, um die richtige Puffergröße zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="06220-117">Alternatively, you can first call `GetILToNativeMapping` with a zero-length `map` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="06220-118">Sie können die Puffergröße dann auf den Wert festlegen, der von `pcMap` zurückgegeben wurde, und `GetILToNativeMapping` erneut aufrufen.</span><span class="sxs-lookup"><span data-stu-id="06220-118">You can then set the buffer size to the value returned in `pcMap` and call `GetILToNativeMapping` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06220-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="06220-119">Requirements</span></span>  

 <span data-ttu-id="06220-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06220-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06220-121">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="06220-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="06220-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06220-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06220-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06220-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06220-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="06220-124">See also</span></span>

- [<span data-ttu-id="06220-125">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="06220-125">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="06220-126">GetILToNativeMapping2-Methode</span><span class="sxs-lookup"><span data-stu-id="06220-126">GetILToNativeMapping2 Method</span></span>](icorprofilerinfo4-getiltonativemapping2-method.md)
- [<span data-ttu-id="06220-127">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="06220-127">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="06220-128">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="06220-128">Profiling</span></span>](index.md)
