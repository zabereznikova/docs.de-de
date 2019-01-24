---
title: ICorProfilerCallback::ClassUnloadStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadStarted
helpviewer_keywords:
- ClassUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ClassUnloadStarted method [.NET Framework profiling]
ms.assetid: bc93bead-f3a9-415c-b919-ddd3ca80facc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 217e0942e523b533656f4d194d2b3e3ec63c6db7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54683348"
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="71e54-102">ICorProfilerCallback::ClassUnloadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="71e54-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>
<span data-ttu-id="71e54-103">Benachrichtigt den Profiler, dass eine Klasse, entladen wird.</span><span class="sxs-lookup"><span data-stu-id="71e54-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71e54-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="71e54-104">Syntax</span></span>  
  
```  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="71e54-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="71e54-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="71e54-106">[in] Identifiziert die Klasse, die entladen wird.</span><span class="sxs-lookup"><span data-stu-id="71e54-106">[in] Identifies the class that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71e54-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="71e54-107">Remarks</span></span>  
 <span data-ttu-id="71e54-108">Der Wert des `classId` gilt nicht für eine informationsanforderung nach der `ClassUnloadStarted` Methodenrückgabe – Dies ist der Profiler letzte Gelegenheit zum Abrufen von Informationen zu dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="71e54-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71e54-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="71e54-109">Requirements</span></span>  
 <span data-ttu-id="71e54-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71e54-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71e54-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="71e54-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="71e54-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71e54-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71e54-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71e54-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71e54-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71e54-114">See also</span></span>
- [<span data-ttu-id="71e54-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71e54-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="71e54-116">ClassUnloadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="71e54-116">ClassUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)
