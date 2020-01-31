---
title: ICorProfilerCallback2::ThreadNameChanged-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.ThreadNameChanged
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::ThreadNameChanged
helpviewer_keywords:
- ThreadNameChanged method [.NET Framework profiling]
- ICorProfilerCallback2::ThreadNameChanged method [.NET Framework profiling]
ms.assetid: c8bbd76d-a9ff-44f2-87a6-be052819da36
topic_type:
- apiref
ms.openlocfilehash: c5182fd44f0cc2ad7b836bbcbddc469c89dbacb7
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865700"
---
# <a name="icorprofilercallback2threadnamechanged-method"></a><span data-ttu-id="a1d76-102">ICorProfilerCallback2::ThreadNameChanged-Methode</span><span class="sxs-lookup"><span data-stu-id="a1d76-102">ICorProfilerCallback2::ThreadNameChanged Method</span></span>
<span data-ttu-id="a1d76-103">Benachrichtigt den Codeprofiler, dass sich der Name eines Threads geändert hat.</span><span class="sxs-lookup"><span data-stu-id="a1d76-103">Notifies the code profiler that the name of a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1d76-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1d76-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadNameChanged(  
    [in] ThreadID threadId,  
    [in] ULONG cchName,  
    [in] WCHAR name[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1d76-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="a1d76-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="a1d76-106">in Die ID des Threads.</span><span class="sxs-lookup"><span data-stu-id="a1d76-106">[in] The ID of the thread.</span></span>  
  
 `cchName`  
 <span data-ttu-id="a1d76-107">in Die Länge des neuen Namens des Threads.</span><span class="sxs-lookup"><span data-stu-id="a1d76-107">[in] The length of the new name of the thread.</span></span>  
  
 `name`  
 <span data-ttu-id="a1d76-108">in Der neue Name des Threads.</span><span class="sxs-lookup"><span data-stu-id="a1d76-108">[in] The new name of the thread.</span></span> <span data-ttu-id="a1d76-109">Der Name wird nicht mit Null beendet.</span><span class="sxs-lookup"><span data-stu-id="a1d76-109">The name is not null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1d76-110">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a1d76-110">Requirements</span></span>  
 <span data-ttu-id="a1d76-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1d76-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1d76-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a1d76-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a1d76-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1d76-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1d76-114">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1d76-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1d76-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1d76-115">See also</span></span>

- [<span data-ttu-id="a1d76-116">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a1d76-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="a1d76-117">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a1d76-117">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
