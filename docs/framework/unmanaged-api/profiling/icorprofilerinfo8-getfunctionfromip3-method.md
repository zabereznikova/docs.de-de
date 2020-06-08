---
title: ICorProfilerInfo8::GetFunctionFromIP3
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetFunctionFromIP3
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 6822757608429ca5f4ef9520ab7574d440b67b26
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495255"
---
# <a name="icorprofilerinfo8getfunctionfromip3-method"></a><span data-ttu-id="9b9ff-102">ICorProfilerInfo8:: GetFunctionFromIP3-Methode</span><span class="sxs-lookup"><span data-stu-id="9b9ff-102">ICorProfilerInfo8::GetFunctionFromIP3 Method</span></span>

<span data-ttu-id="9b9ff-103">Ordnet einen Anweisungs Zeiger für verwalteten Code einem functionId-Wert zu.</span><span class="sxs-lookup"><span data-stu-id="9b9ff-103">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="9b9ff-104">Diese Methode funktioniert sowohl für dynamische als auch für nicht dynamische Methoden.</span><span class="sxs-lookup"><span data-stu-id="9b9ff-104">This method works for both dynamic and non-dynamic methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="9b9ff-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b9ff-105">Syntax</span></span>

```cpp
HRESULT GetFunctionFromIP3([in] LPCBYTE ip,
                           [out] FunctionID *functionId,
                           [out] ReJITID * pReJitId);
```

## <a name="parameters"></a><span data-ttu-id="9b9ff-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9b9ff-106">Parameters</span></span>

- `ip`

  <span data-ttu-id="9b9ff-107">\[in] der Anweisungs Zeiger in verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="9b9ff-107">\[in] The instruction pointer in managed code.</span></span>

- `pFunctionId`

  <span data-ttu-id="9b9ff-108">\[out] die Funktions-ID.</span><span class="sxs-lookup"><span data-stu-id="9b9ff-108">\[out] The function ID.</span></span>

- `pReJitId`

  <span data-ttu-id="9b9ff-109">\[out] die Identität der neu kompilierten JIT-Version der Funktion.</span><span class="sxs-lookup"><span data-stu-id="9b9ff-109">\[out] The identity of the JIT-recompiled version of the function.</span></span>

## <a name="remarks"></a><span data-ttu-id="9b9ff-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9b9ff-110">Remarks</span></span>

<span data-ttu-id="9b9ff-111">Diese Methode funktioniert sowohl für dynamische als auch für nicht dynamische Methoden.</span><span class="sxs-lookup"><span data-stu-id="9b9ff-111">This method works for both dynamic and non-dynamic methods.</span></span> <span data-ttu-id="9b9ff-112">Es ist eine supermenge von [GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md), die nur für Funktionen mit Metadaten funktioniert.</span><span class="sxs-lookup"><span data-stu-id="9b9ff-112">It is a superset of [GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md), which only works for functions with metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="9b9ff-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9b9ff-113">Requirements</span></span>

<span data-ttu-id="9b9ff-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b9ff-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="9b9ff-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9b9ff-115">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="9b9ff-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b9ff-116">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="9b9ff-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9b9ff-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="9b9ff-118">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="9b9ff-118">See also</span></span>

- [<span data-ttu-id="9b9ff-119">ICorProfilerInfo8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b9ff-119">ICorProfilerInfo8 Interface</span></span>](icorprofilerinfo8-interface.md)
