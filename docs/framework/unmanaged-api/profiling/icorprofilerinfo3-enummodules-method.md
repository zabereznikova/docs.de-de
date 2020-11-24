---
title: ICorProfilerInfo3::EnumModules-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.EnumModules Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::EnumModules
helpviewer_keywords:
- ICorProfilerInfo3::EnumModules method [.NET Framework profiling]
- EnumModules method [.NET Framework profiling]
ms.assetid: 1bf00b42-69da-4019-91b3-bf88026e83fb
topic_type:
- apiref
ms.openlocfilehash: 698f6abc872a7e072ae47520386aa9c7ddfb44fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681469"
---
# <a name="icorprofilerinfo3enummodules-method"></a><span data-ttu-id="34667-102">ICorProfilerInfo3::EnumModules-Methode</span><span class="sxs-lookup"><span data-stu-id="34667-102">ICorProfilerInfo3::EnumModules Method</span></span>

<span data-ttu-id="34667-103">Gibt einen Enumerator zurück, der Methoden zum sequenziellen Iterieren durch eine Auflistung von verwalteten Modulen bereitstellt, die in die Anwendung geladen werden.</span><span class="sxs-lookup"><span data-stu-id="34667-103">Returns an enumerator that provides methods to sequentially iterate through a collection of managed modules that are loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34667-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="34667-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModules([out] ICorProfilerModuleEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34667-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="34667-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="34667-106">vorgenommen Ein Zeiger auf eine [icorprofilermoduleferum](icorprofilermoduleenum-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="34667-106">[out] A pointer to an [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34667-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="34667-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34667-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="34667-108">Requirements</span></span>  

 <span data-ttu-id="34667-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34667-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34667-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="34667-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="34667-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34667-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34667-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34667-112">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34667-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="34667-113">See also</span></span>

- [<span data-ttu-id="34667-114">ICorProfilerFunctionEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="34667-114">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="34667-115">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="34667-115">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="34667-116">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="34667-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="34667-117">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="34667-117">Profiling</span></span>](index.md)
