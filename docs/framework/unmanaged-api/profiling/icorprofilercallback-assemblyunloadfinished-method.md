---
title: ICorProfilerCallback::AssemblyUnloadFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadFinished
helpviewer_keywords:
- AssemblyUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::AssemblyUnloadFinished method [.NET Framework profiling]
ms.assetid: 53fca564-84b1-44d4-9e21-17a492d2aae7
topic_type:
- apiref
ms.openlocfilehash: 01404d23707be90b6b15cf741632400d49f164de
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445151"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a><span data-ttu-id="daf1b-102">ICorProfilerCallback::AssemblyUnloadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="daf1b-102">ICorProfilerCallback::AssemblyUnloadFinished Method</span></span>
<span data-ttu-id="daf1b-103">Benachrichtigt den Profiler, dass eine Assembly entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="daf1b-103">Notifies the profiler that an assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daf1b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="daf1b-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="daf1b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="daf1b-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="daf1b-106">in Identifiziert die Assembly, die entladen wird.</span><span class="sxs-lookup"><span data-stu-id="daf1b-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="daf1b-107">in Ein HRESULT, das angibt, ob die Assembly erfolgreich entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="daf1b-107">[in] An HRESULT that indicates whether the assembly was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="daf1b-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="daf1b-108">Remarks</span></span>  
 <span data-ttu-id="daf1b-109">Der Wert `assemblyId` ist für eine Informationsanforderung nicht gültig, nachdem die [ICorProfilerCallback:: AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) -Methode zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="daf1b-109">The value of `assemblyId` is not valid for an information request after the [ICorProfilerCallback::AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="daf1b-110">Einige Teile des Entladen der Assembly können nach dem `AssemblyUnloadFinished` Rückruf fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="daf1b-110">Some parts of unloading the assembly might continue after the `AssemblyUnloadFinished` callback.</span></span> <span data-ttu-id="daf1b-111">Ein HRESULT-Fehler in `hrStatus` deutet auf einen Fehler hin.</span><span class="sxs-lookup"><span data-stu-id="daf1b-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="daf1b-112">Ein HRESULT-Erfolg in `hrStatus` gibt jedoch nur an, dass der erste Teil des Entladen der Assembly erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="daf1b-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="daf1b-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="daf1b-113">Requirements</span></span>  
 <span data-ttu-id="daf1b-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="daf1b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daf1b-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="daf1b-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="daf1b-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="daf1b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="daf1b-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="daf1b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daf1b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="daf1b-118">See also</span></span>

- [<span data-ttu-id="daf1b-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="daf1b-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
