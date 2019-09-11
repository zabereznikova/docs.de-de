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
ms.openlocfilehash: df9ecc9bc355c12f993763820eb5065ba8bcc36b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855915"
---
# <a name="icorprofilerinfo8getfunctionfromip3-method"></a><span data-ttu-id="c5fb0-102">ICorProfilerInfo8:: GetFunctionFromIP3-Methode</span><span class="sxs-lookup"><span data-stu-id="c5fb0-102">ICorProfilerInfo8::GetFunctionFromIP3 Method</span></span>

<span data-ttu-id="c5fb0-103">Ordnet einen Anweisungs Zeiger für verwalteten Code einem functionId-Wert zu.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-103">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="c5fb0-104">Diese Methode funktioniert sowohl für dynamische als auch für nicht dynamische Methoden.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-104">This method works for both dynamic and non-dynamic methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="c5fb0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c5fb0-105">Syntax</span></span>

```cpp
HRESULT GetFunctionFromIP3([in] LPCBYTE ip,
                           [out] FunctionID *functionId,
                           [out] ReJITID * pReJitId);
```

#### <a name="parameters"></a><span data-ttu-id="c5fb0-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="c5fb0-106">Parameters</span></span>

`ip` \
<span data-ttu-id="c5fb0-107">in Der Anweisungs Zeiger in verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-107">[in] The instruction pointer in managed code.</span></span>

`pFunctionId` \
<span data-ttu-id="c5fb0-108">vorgenommen Die Funktions-ID.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-108">[out] The function ID.</span></span>

`pReJitId` \
<span data-ttu-id="c5fb0-109">vorgenommen Die Identität der neu kompilierten JIT-Version der Funktion.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-109">[out] The identity of the JIT-recompiled version of the function.</span></span>

## <a name="remarks"></a><span data-ttu-id="c5fb0-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c5fb0-110">Remarks</span></span>

<span data-ttu-id="c5fb0-111">Diese Methode funktioniert sowohl für dynamische als auch für nicht dynamische Methoden.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-111">This method works for both dynamic and non-dynamic methods.</span></span> <span data-ttu-id="c5fb0-112">Es ist eine supermenge von [GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md), die nur für Funktionen mit Metadaten funktioniert.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-112">It is a superset of [GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md), which only works for functions with metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="c5fb0-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c5fb0-113">Requirements</span></span>

<span data-ttu-id="c5fb0-114">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5fb0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="c5fb0-115">**Header:** Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="c5fb0-115">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="c5fb0-116">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5fb0-116">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="c5fb0-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c5fb0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c5fb0-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5fb0-118">See also</span></span>

- [<span data-ttu-id="c5fb0-119">ICorProfilerInfo8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5fb0-119">ICorProfilerInfo8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)
