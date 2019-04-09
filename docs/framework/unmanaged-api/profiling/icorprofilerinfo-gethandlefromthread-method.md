---
title: ICorProfilerInfo::GetHandleFromThread-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetHandleFromThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetHandleFromThread
helpviewer_keywords:
- GetHandleFromThread method [.NET Framework profiling]
- ICorProfilerInfo::GetHandleFromThread method [.NET Framework profiling]
ms.assetid: 36cdc9f5-7579-4cd2-aa36-fc05c741584c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8fc26ad9b25ad243bf868d6ef3155360509e6483
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59185743"
---
# <a name="icorprofilerinfogethandlefromthread-method"></a><span data-ttu-id="3a929-102">ICorProfilerInfo::GetHandleFromThread-Methode</span><span class="sxs-lookup"><span data-stu-id="3a929-102">ICorProfilerInfo::GetHandleFromThread Method</span></span>
<span data-ttu-id="3a929-103">Ordnet die ID eines Threads ein Win32-Thread-Handle.</span><span class="sxs-lookup"><span data-stu-id="3a929-103">Maps the ID of a thread to a Win32 thread handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a929-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a929-104">Syntax</span></span>  
  
```  
HRESULT GetHandleFromThread(  
    [in]  ThreadID threadId,  
    [out] HANDLE  *phThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a929-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3a929-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="3a929-106">[in] Die Thread-ID zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3a929-106">[in] The thread ID to be mapped.</span></span>  
  
 `phThread`  
 <span data-ttu-id="3a929-107">[out] Ein Zeiger auf ein Win32-Thread-Handle.</span><span class="sxs-lookup"><span data-stu-id="3a929-107">[out] A pointer to a Win32 thread handle.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a929-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3a929-108">Remarks</span></span>  
 <span data-ttu-id="3a929-109">Der Profiler muss die Win32 Aufrufen `DuplicateHandle` Funktion auf den Ziehpunkt, bevor Sie ihn verwenden.</span><span class="sxs-lookup"><span data-stu-id="3a929-109">The profiler must call the Win32 `DuplicateHandle` function on the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a929-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3a929-110">Requirements</span></span>  
 <span data-ttu-id="3a929-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a929-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a929-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3a929-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3a929-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a929-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3a929-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="3a929-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3a929-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a929-115">See also</span></span>

- [<span data-ttu-id="3a929-116">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3a929-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
