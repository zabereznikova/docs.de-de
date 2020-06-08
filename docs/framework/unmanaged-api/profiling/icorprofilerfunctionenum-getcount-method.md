---
title: ICorProfilerFunctionEnum::GetCount-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.GetCount Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::GetCount
helpviewer_keywords:
- ICorProfilerFunctionEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 62ec65e3-3e9d-400b-ae61-d24b8963995b
topic_type:
- apiref
ms.openlocfilehash: 137b1da853535985b2fd383d52f0bcfc48f728ed
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503093"
---
# <a name="icorprofilerfunctionenumgetcount-method"></a><span data-ttu-id="87b89-102">ICorProfilerFunctionEnum::GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="87b89-102">ICorProfilerFunctionEnum::GetCount Method</span></span>
<span data-ttu-id="87b89-103">Ruft die Anzahl der Funktionen ab, die von der Anwendung oder erzwungen vom Profiler geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="87b89-103">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87b89-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="87b89-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87b89-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="87b89-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="87b89-106">vorgenommen Die Anzahl der Funktionen, die geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="87b89-106">[out] The number of functions that were loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87b89-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="87b89-107">Requirements</span></span>  
 <span data-ttu-id="87b89-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87b89-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87b89-109">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="87b89-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="87b89-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87b89-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87b89-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87b89-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87b89-112">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="87b89-112">See also</span></span>

- [<span data-ttu-id="87b89-113">ICorProfilerFunctionEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="87b89-113">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="87b89-114">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="87b89-114">Profiling Interfaces</span></span>](profiling-interfaces.md)
