---
title: ICorProfilerInfo3::GetStringLayout2-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.GetStringLayout2 Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::GetStringLayout2
helpviewer_keywords:
- ICorProfilerInfo3::GetStringLayout2 method [.NET Framework profiling]
- GetStringLayout2 method [.NET Framework profiling]
ms.assetid: 1a268496-ee51-4d84-8700-ee56fd0c499d
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 97f4ab9eefa8bf1f2b3a5057f24b6a940ba91f41
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo3getstringlayout2-method"></a><span data-ttu-id="707e6-102">ICorProfilerInfo3::GetStringLayout2-Methode</span><span class="sxs-lookup"><span data-stu-id="707e6-102">ICorProfilerInfo3::GetStringLayout2 Method</span></span>
<span data-ttu-id="707e6-103">Ruft Informationen zum Layout eines Zeichenfolgenobjekts ab.</span><span class="sxs-lookup"><span data-stu-id="707e6-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="707e6-104">Diese Methode hat Vorrang vor den [ICorProfilerInfo2:: GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="707e6-104">This method supersedes the [ICorProfilerInfo2::GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="707e6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="707e6-105">Syntax</span></span>  
  
```  
HRESULT GetStringLayout2(  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="707e6-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="707e6-106">Parameters</span></span>  
 `pStringLengthOffset`  
 <span data-ttu-id="707e6-107">[out] Ein Zeiger auf den Offset des Speicherorts, relativ zu den `ObjectID` Zeiger, der die Länge der Zeichenfolge selbst speichert.</span><span class="sxs-lookup"><span data-stu-id="707e6-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="707e6-108">Die Länge wird gespeichert, als eine `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="707e6-108">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="707e6-109">[out] Ein Zeiger auf den Offset des Puffers, relativ zu den `ObjectID` Zeiger, der die Zeichenfolge mit Breitzeichen speichert.</span><span class="sxs-lookup"><span data-stu-id="707e6-109">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, which stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="707e6-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="707e6-110">Remarks</span></span>  
 <span data-ttu-id="707e6-111">Zeichenfolgen können oder können nicht Null-terminiert sein.</span><span class="sxs-lookup"><span data-stu-id="707e6-111">Strings may or may not be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="707e6-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="707e6-112">Requirements</span></span>  
 <span data-ttu-id="707e6-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="707e6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="707e6-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="707e6-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="707e6-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="707e6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="707e6-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="707e6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="707e6-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="707e6-117">See Also</span></span>  
 [<span data-ttu-id="707e6-118">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="707e6-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="707e6-119">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="707e6-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
