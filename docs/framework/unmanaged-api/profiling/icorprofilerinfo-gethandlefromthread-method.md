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
ms.openlocfilehash: e508ccd81d25aa3d303456fa88554903ec71d633
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439068"
---
# <a name="icorprofilerinfogethandlefromthread-method"></a><span data-ttu-id="66743-102">ICorProfilerInfo::GetHandleFromThread-Methode</span><span class="sxs-lookup"><span data-stu-id="66743-102">ICorProfilerInfo::GetHandleFromThread Method</span></span>
<span data-ttu-id="66743-103">Ordnet die ID eines Threads einem Win32-Thread Handle zu.</span><span class="sxs-lookup"><span data-stu-id="66743-103">Maps the ID of a thread to a Win32 thread handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66743-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="66743-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandleFromThread(  
    [in]  ThreadID threadId,  
    [out] HANDLE  *phThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66743-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="66743-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="66743-106">in Die zuzuordnende Thread-ID.</span><span class="sxs-lookup"><span data-stu-id="66743-106">[in] The thread ID to be mapped.</span></span>  
  
 `phThread`  
 <span data-ttu-id="66743-107">vorgenommen Ein Zeiger auf ein Win32-Thread handle.</span><span class="sxs-lookup"><span data-stu-id="66743-107">[out] A pointer to a Win32 thread handle.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66743-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="66743-108">Remarks</span></span>  
 <span data-ttu-id="66743-109">Der Profiler muss die Win32-`DuplicateHandle`-Funktion für das Handle vor der Verwendung aufruft.</span><span class="sxs-lookup"><span data-stu-id="66743-109">The profiler must call the Win32 `DuplicateHandle` function on the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66743-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="66743-110">Requirements</span></span>  
 <span data-ttu-id="66743-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66743-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66743-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="66743-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="66743-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66743-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66743-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66743-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66743-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66743-115">See also</span></span>

- [<span data-ttu-id="66743-116">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="66743-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
