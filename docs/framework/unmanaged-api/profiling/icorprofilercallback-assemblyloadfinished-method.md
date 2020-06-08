---
title: ICorProfilerCallback::AssemblyLoadFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadFinished
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadFinished method [.NET Framework profiling]
- AssemblyLoadFinished method [.NET Framework profiling]
ms.assetid: 86d98f39-52e6-4c61-a625-9760f695ff12
topic_type:
- apiref
ms.openlocfilehash: ce4a842bc71ff144e46efb0d6f7068dfca9d207d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500441"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="85712-102">ICorProfilerCallback::AssemblyLoadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="85712-102">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>
<span data-ttu-id="85712-103">Benachrichtigt den Profiler, dass eine Assembly den Ladevorgang abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="85712-103">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85712-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="85712-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85712-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="85712-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="85712-106">\[in] identifiziert die Assembly, die geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="85712-106">\[in] Identifies the assembly that was loaded.</span></span>

- `hrStatus`

  <span data-ttu-id="85712-107">\[in] ein HRESULT, das angibt, ob die Assembly erfolgreich geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="85712-107">\[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="85712-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="85712-108">Remarks</span></span>  
 <span data-ttu-id="85712-109">Der Wert von `assemblyId` ist für eine Informationsanforderung erst gültig, wenn die- `AssemblyLoadFinished` Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="85712-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="85712-110">Einige Teile des Ladens der Assembly können nach dem Rückruf fortgesetzt werden `AssemblyLoadFinished` .</span><span class="sxs-lookup"><span data-stu-id="85712-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="85712-111">Ein Fehler HRESULT in `hrStatus` weist auf einen Fehler hin.</span><span class="sxs-lookup"><span data-stu-id="85712-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="85712-112">Ein HRESULT-Erfolg in `hrStatus` gibt jedoch nur an, dass der erste Teil des Ladens der Assembly erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="85712-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85712-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="85712-113">Requirements</span></span>  
 <span data-ttu-id="85712-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85712-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85712-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="85712-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="85712-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85712-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85712-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85712-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85712-118">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="85712-118">See also</span></span>

- [<span data-ttu-id="85712-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85712-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
