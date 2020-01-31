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
ms.openlocfilehash: cd1f3982fe1439135bf96579370a5a798c61dd2e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863784"
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="02296-102">ICorProfilerInfo::GetFunctionFromIP-Methode</span><span class="sxs-lookup"><span data-stu-id="02296-102">ICorProfilerInfo::GetFunctionFromIP Method</span></span>
<span data-ttu-id="02296-103">Ordnet einen Anweisungs Zeiger für verwalteten Code einem `FunctionID`zu.</span><span class="sxs-lookup"><span data-stu-id="02296-103">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02296-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="02296-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02296-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="02296-105">Parameters</span></span>

- `ip`

  <span data-ttu-id="02296-106">\[in] der Anweisungs Zeiger in verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="02296-106">\[in] The instruction pointer in managed code.</span></span>

- `pFunctionId`

  <span data-ttu-id="02296-107">\[out] die zurückgegebene Funktions-ID.</span><span class="sxs-lookup"><span data-stu-id="02296-107">\[out] The returned function ID.</span></span>

## <a name="requirements"></a><span data-ttu-id="02296-108">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="02296-108">Requirements</span></span>  
 <span data-ttu-id="02296-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02296-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02296-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="02296-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="02296-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02296-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02296-112">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02296-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02296-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02296-113">See also</span></span>

- [<span data-ttu-id="02296-114">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="02296-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
