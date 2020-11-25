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
ms.openlocfilehash: 516a12b7a4457a0f67da24294ad96fb79d1aa5aa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707515"
---
# <a name="icorprofilerinfogetthreadinfo-method"></a><span data-ttu-id="5c3ec-102">ICorProfilerInfo::GetThreadInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="5c3ec-102">ICorProfilerInfo::GetThreadInfo Method</span></span>

<span data-ttu-id="5c3ec-103">Ruft die aktuelle Win32-Thread Identität für den angegebenen Thread ab.</span><span class="sxs-lookup"><span data-stu-id="5c3ec-103">Gets the current Win32 thread identity for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c3ec-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5c3ec-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadInfo(  
    [in]  ThreadID threadId,  
    [out] DWORD    *pdwWin32ThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c3ec-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5c3ec-105">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="5c3ec-106">in Die ID des Threads, für den die aktuelle Win32-ID angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c3ec-106">[in] The ID of the thread for which to get the current Win32 ID.</span></span>  
  
 `pdwWin32ThreadId`  
 <span data-ttu-id="5c3ec-107">vorgenommen Ein Zeiger auf die aktuelle Win32-Thread-ID des angegebenen Threads.</span><span class="sxs-lookup"><span data-stu-id="5c3ec-107">[out] A pointer to the specified thread's current Win32 thread ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c3ec-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5c3ec-108">Requirements</span></span>  

 <span data-ttu-id="5c3ec-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c3ec-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c3ec-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5c3ec-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5c3ec-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c3ec-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c3ec-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c3ec-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c3ec-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5c3ec-113">See also</span></span>

- [<span data-ttu-id="5c3ec-114">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5c3ec-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
