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
ms.openlocfilehash: 734ae1d14d02d47c7d3126f1b4cf55dcb4ad151b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866623"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a><span data-ttu-id="49dcf-102">ICorProfilerCallback::AssemblyUnloadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="49dcf-102">ICorProfilerCallback::AssemblyUnloadFinished Method</span></span>
<span data-ttu-id="49dcf-103">Benachrichtigt den Profiler, dass eine Assembly entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="49dcf-103">Notifies the profiler that an assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49dcf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="49dcf-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49dcf-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="49dcf-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="49dcf-106">\[in] identifiziert die Assembly, die entladen wird.</span><span class="sxs-lookup"><span data-stu-id="49dcf-106">\[in] Identifies the assembly that is being unloaded.</span></span>

- `hrStatus`

  <span data-ttu-id="49dcf-107">\[in] ein HRESULT, das angibt, ob die Assembly erfolgreich entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="49dcf-107">\[in] An HRESULT that indicates whether the assembly was unloaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="49dcf-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="49dcf-108">Remarks</span></span>  
 <span data-ttu-id="49dcf-109">Der Wert `assemblyId` ist für eine Informationsanforderung nicht gültig, nachdem die [ICorProfilerCallback:: AssemblyUnloadStarted](icorprofilercallback-assemblyunloadstarted-method.md) -Methode zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="49dcf-109">The value of `assemblyId` is not valid for an information request after the [ICorProfilerCallback::AssemblyUnloadStarted](icorprofilercallback-assemblyunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="49dcf-110">Einige Teile des Entladen der Assembly können nach dem `AssemblyUnloadFinished` Rückruf fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="49dcf-110">Some parts of unloading the assembly might continue after the `AssemblyUnloadFinished` callback.</span></span> <span data-ttu-id="49dcf-111">Ein HRESULT-Fehler in `hrStatus` deutet auf einen Fehler hin.</span><span class="sxs-lookup"><span data-stu-id="49dcf-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="49dcf-112">Ein HRESULT-Erfolg in `hrStatus` gibt jedoch nur an, dass der erste Teil des Entladen der Assembly erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="49dcf-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49dcf-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="49dcf-113">Requirements</span></span>  
 <span data-ttu-id="49dcf-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49dcf-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49dcf-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="49dcf-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="49dcf-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49dcf-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49dcf-117">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49dcf-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49dcf-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49dcf-118">See also</span></span>

- [<span data-ttu-id="49dcf-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49dcf-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
