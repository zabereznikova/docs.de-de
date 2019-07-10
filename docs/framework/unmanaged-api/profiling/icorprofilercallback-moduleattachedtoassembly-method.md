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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3345e2e87ba41f750031deed2d15e13dbe4f06c8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769292"
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a><span data-ttu-id="4bdfa-102">ICorProfilerCallback::ModuleAttachedToAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="4bdfa-102">ICorProfilerCallback::ModuleAttachedToAssembly Method</span></span>
<span data-ttu-id="4bdfa-103">Benachrichtigt den Profiler, dass ein Modul, dessen übergeordnete Assembly der angeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="4bdfa-103">Notifies the profiler that a module is being attached to its parent assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bdfa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4bdfa-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4bdfa-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4bdfa-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="4bdfa-106">[in] Die ID des Moduls, die angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="4bdfa-106">[in] The ID of the module that is being attached.</span></span>  
  
 `AssemblyId`  
 <span data-ttu-id="4bdfa-107">[in] Die ID der übergeordneten Assembly, die das Modul zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="4bdfa-107">[in] The ID of the parent assembly to which the module is attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4bdfa-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4bdfa-108">Remarks</span></span>  
 <span data-ttu-id="4bdfa-109">Ein Modul kann durch eine Importadresstabelle (IAT), geladen werden, durch einen Aufruf von `LoadLibrary`, oder über einen Metadatenverweis.</span><span class="sxs-lookup"><span data-stu-id="4bdfa-109">A module can be loaded through an import address table (IAT), through a call to `LoadLibrary`, or through a metadata reference.</span></span> <span data-ttu-id="4bdfa-110">Daher hat das common Language Runtime (CLR)-Ladeprogramm mehrere Codepfade zur Bestimmung der Assembly, in der ein Modul befindet.</span><span class="sxs-lookup"><span data-stu-id="4bdfa-110">As a result, the common language runtime (CLR) loader has multiple code paths for determining the assembly in which a module lives.</span></span> <span data-ttu-id="4bdfa-111">Daher ist es möglich, dass Sie nach [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) aufgerufen wird, wird das Modul ist nicht bekannt, welche Assembly ist, und die übergeordnete Assembly-ID ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="4bdfa-111">Therefore, it is possible that after [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) is called, the module does not know what assembly it is in and getting the parent assembly ID is not possible.</span></span> <span data-ttu-id="4bdfa-112">Die `ModuleAttachedToAssembly` Methode wird aufgerufen, wenn das Modul, um die übergeordnete Assembly und die übergeordnete Assembly angefügt wird-ID abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="4bdfa-112">The `ModuleAttachedToAssembly` method is called when the module is attached to its parent assembly and its parent assembly ID can be obtained.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bdfa-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4bdfa-113">Requirements</span></span>  
 <span data-ttu-id="4bdfa-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bdfa-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bdfa-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4bdfa-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4bdfa-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4bdfa-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4bdfa-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bdfa-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bdfa-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4bdfa-118">See also</span></span>

- [<span data-ttu-id="4bdfa-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4bdfa-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
