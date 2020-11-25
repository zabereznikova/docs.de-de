---
title: ICorProfilerCallback::ModuleAttachedToAssembly-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleAttachedToAssembly
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly
helpviewer_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly method [.NET Framework profiling]
- ModuleAttachedToAssembly method [.NET Framework profiling]
ms.assetid: b595798a-5d40-4cac-ab4f-911c61d2c5d2
topic_type:
- apiref
ms.openlocfilehash: bcf5c5c9044a30fc8259dbc54bad8f3141f0f926
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733112"
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a><span data-ttu-id="56c56-102">ICorProfilerCallback::ModuleAttachedToAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="56c56-102">ICorProfilerCallback::ModuleAttachedToAssembly Method</span></span>

<span data-ttu-id="56c56-103">Benachrichtigt den Profiler, dass ein Modul an die übergeordnete Assembly angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="56c56-103">Notifies the profiler that a module is being attached to its parent assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56c56-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="56c56-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56c56-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="56c56-105">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="56c56-106">in Die ID des Moduls, das angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="56c56-106">[in] The ID of the module that is being attached.</span></span>  
  
 `AssemblyId`  
 <span data-ttu-id="56c56-107">in Die ID der übergeordneten Assembly, an die das Modul angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="56c56-107">[in] The ID of the parent assembly to which the module is attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56c56-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="56c56-108">Remarks</span></span>  

 <span data-ttu-id="56c56-109">Ein Modul kann über eine Import Adress Tabelle (IAT), über einen-Rückruf `LoadLibrary` oder über einen Metadatenverweis geladen werden.</span><span class="sxs-lookup"><span data-stu-id="56c56-109">A module can be loaded through an import address table (IAT), through a call to `LoadLibrary`, or through a metadata reference.</span></span> <span data-ttu-id="56c56-110">Daher verfügt das Common Language Runtime (CLR)-Lade Modul über mehrere Codepfade zum Ermitteln der Assembly, in der sich ein Modul befindet.</span><span class="sxs-lookup"><span data-stu-id="56c56-110">As a result, the common language runtime (CLR) loader has multiple code paths for determining the assembly in which a module lives.</span></span> <span data-ttu-id="56c56-111">Daher ist es möglich, dass das Modul nach dem Aufruf von [ICorProfilerCallback:: moduleloadend](icorprofilercallback-moduleloadfinished-method.md) nicht weiß, in welcher Assembly es sich befindet und die übergeordnete Assembly-ID nicht abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="56c56-111">Therefore, it is possible that after [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) is called, the module does not know what assembly it is in and getting the parent assembly ID is not possible.</span></span> <span data-ttu-id="56c56-112">Die `ModuleAttachedToAssembly` -Methode wird aufgerufen, wenn das Modul an die übergeordnete Assembly angefügt wird und die übergeordnete Assembly-ID abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="56c56-112">The `ModuleAttachedToAssembly` method is called when the module is attached to its parent assembly and its parent assembly ID can be obtained.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56c56-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="56c56-113">Requirements</span></span>  

 <span data-ttu-id="56c56-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56c56-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56c56-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="56c56-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="56c56-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56c56-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="56c56-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56c56-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56c56-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56c56-118">See also</span></span>

- [<span data-ttu-id="56c56-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="56c56-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
