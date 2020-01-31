---
title: ICorProfilerModuleEnum::GetCount-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.GetCount Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::GetCount
helpviewer_keywords:
- ICorProfilerModuleEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: f0a4a5e0-4689-474b-b0f4-37ca0639c918
topic_type:
- apiref
ms.openlocfilehash: 772a7c08c934fda59a2764e1fbe22d3d2b08a620
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861501"
---
# <a name="icorprofilermoduleenumgetcount-method"></a><span data-ttu-id="7bf7c-102">ICorProfilerModuleEnum::GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="7bf7c-102">ICorProfilerModuleEnum::GetCount Method</span></span>
<span data-ttu-id="7bf7c-103">Ruft die Anzahl der verwalteten Module ab, die in die Anwendung geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="7bf7c-103">Gets the number of managed modules that were loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bf7c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7bf7c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bf7c-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="7bf7c-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="7bf7c-106">vorgenommen Die Anzahl der Lauf Zeit Module in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="7bf7c-106">[out] The number of runtime modules in the collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bf7c-107">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7bf7c-107">Requirements</span></span>  
 <span data-ttu-id="7bf7c-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7bf7c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bf7c-109">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7bf7c-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7bf7c-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7bf7c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7bf7c-111">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bf7c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bf7c-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7bf7c-112">See also</span></span>

- [<span data-ttu-id="7bf7c-113">ICorProfilerModuleEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7bf7c-113">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="7bf7c-114">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="7bf7c-114">Profiling Interfaces</span></span>](profiling-interfaces.md)
