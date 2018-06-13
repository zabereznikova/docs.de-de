---
title: ICorProfilerInfo::GetThreadInfo-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetThreadInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetThreadInfo
helpviewer_keywords:
- ICorProfilerInfo::GetThreadInfo method [.NET Framework profiling]
- GetThreadInfo method [.NET Framework profiling]
ms.assetid: fc994fef-65c9-432a-84cb-66c8141147e7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f68565977551a54244f3caf6a0250f67005a6ecf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452880"
---
# <a name="icorprofilerinfogetthreadinfo-method"></a><span data-ttu-id="0b4b9-102">ICorProfilerInfo::GetThreadInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="0b4b9-102">ICorProfilerInfo::GetThreadInfo Method</span></span>
<span data-ttu-id="0b4b9-103">Ruft die aktuelle Win32-Thread-Identität für den angegebenen Thread ab.</span><span class="sxs-lookup"><span data-stu-id="0b4b9-103">Gets the current Win32 thread identity for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b4b9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b4b9-104">Syntax</span></span>  
  
```  
HRESULT GetThreadInfo(  
    [in]  ThreadID threadId,  
    [out] DWORD    *pdwWin32ThreadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0b4b9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0b4b9-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="0b4b9-106">[in] Die ID des Threads für die aktuelle Win32-ID abgerufen</span><span class="sxs-lookup"><span data-stu-id="0b4b9-106">[in] The ID of the thread for which to get the current Win32 ID.</span></span>  
  
 `pdwWin32ThreadId`  
 <span data-ttu-id="0b4b9-107">[out] Ein Zeiger auf den angegebenen Thread aktuelle Win32-Thread-ID.</span><span class="sxs-lookup"><span data-stu-id="0b4b9-107">[out] A pointer to the specified thread's current Win32 thread ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b4b9-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0b4b9-108">Requirements</span></span>  
 <span data-ttu-id="0b4b9-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b4b9-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b4b9-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0b4b9-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0b4b9-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b4b9-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b4b9-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b4b9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b4b9-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b4b9-113">See Also</span></span>  
 [<span data-ttu-id="0b4b9-114">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0b4b9-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
