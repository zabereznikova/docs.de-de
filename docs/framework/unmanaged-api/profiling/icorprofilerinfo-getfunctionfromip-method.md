---
title: ICorProfilerInfo::GetFunctionFromIP-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetFunctionFromIP
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetFunctionFromIP
helpviewer_keywords:
- GetFunctionFromIP method [.NET Framework profiling]
- ICorProfilerInfo::GetFunctionFromIP method [.NET Framework profiling]
ms.assetid: f069802a-198f-46dd-9f09-4f77adffc9ba
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3712187d74cfa180b3cd91f4cee1e9318537b6b0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="28a5f-102">ICorProfilerInfo::GetFunctionFromIP-Methode</span><span class="sxs-lookup"><span data-stu-id="28a5f-102">ICorProfilerInfo::GetFunctionFromIP Method</span></span>
<span data-ttu-id="28a5f-103">Ordnet einen verwalteten Code Anweisungszeiger einen `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="28a5f-103">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28a5f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="28a5f-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="28a5f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="28a5f-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="28a5f-106">[in] Der Anweisungszeiger in verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="28a5f-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="28a5f-107">[out] Die zurückgegebene Funktion-ID.</span><span class="sxs-lookup"><span data-stu-id="28a5f-107">[out] The returned function ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28a5f-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="28a5f-108">Requirements</span></span>  
 <span data-ttu-id="28a5f-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28a5f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28a5f-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="28a5f-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="28a5f-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28a5f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28a5f-112">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28a5f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28a5f-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28a5f-113">See Also</span></span>  
 [<span data-ttu-id="28a5f-114">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="28a5f-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
