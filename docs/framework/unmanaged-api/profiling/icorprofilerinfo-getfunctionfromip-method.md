---
title: ICorProfilerInfo::GetFunctionFromIP-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionFromIP
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionFromIP
helpviewer_keywords:
- GetFunctionFromIP method [.NET Framework profiling]
- ICorProfilerInfo::GetFunctionFromIP method [.NET Framework profiling]
ms.assetid: f069802a-198f-46dd-9f09-4f77adffc9ba
topic_type:
- apiref
ms.openlocfilehash: 4a7e21ae60253c741b57674212e0ecabdd844d2d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722557"
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="c41d6-102">ICorProfilerInfo::GetFunctionFromIP-Methode</span><span class="sxs-lookup"><span data-stu-id="c41d6-102">ICorProfilerInfo::GetFunctionFromIP Method</span></span>

<span data-ttu-id="c41d6-103">Ordnet einen Anweisungs Zeiger für verwalteten Code einem zu `FunctionID` .</span><span class="sxs-lookup"><span data-stu-id="c41d6-103">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c41d6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c41d6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c41d6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c41d6-105">Parameters</span></span>

- `ip`

  <span data-ttu-id="c41d6-106">\[in] der Anweisungs Zeiger in verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="c41d6-106">\[in] The instruction pointer in managed code.</span></span>

- `pFunctionId`

  <span data-ttu-id="c41d6-107">\[out] die zurückgegebene Funktions-ID.</span><span class="sxs-lookup"><span data-stu-id="c41d6-107">\[out] The returned function ID.</span></span>

## <a name="requirements"></a><span data-ttu-id="c41d6-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c41d6-108">Requirements</span></span>  

 <span data-ttu-id="c41d6-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c41d6-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c41d6-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c41d6-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c41d6-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c41d6-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c41d6-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c41d6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c41d6-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c41d6-113">See also</span></span>

- [<span data-ttu-id="c41d6-114">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c41d6-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
