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
ms.openlocfilehash: 791827b9c4b60cb2ee963881bc8e1a6131cd00fb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992198"
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a><span data-ttu-id="f46cb-102">ICorProfilerCallback::ModuleAttachedToAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="f46cb-102">ICorProfilerCallback::ModuleAttachedToAssembly Method</span></span>
<span data-ttu-id="f46cb-103">Benachrichtigt den Profiler, dass ein Modul, dessen übergeordnete Assembly der angeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="f46cb-103">Notifies the profiler that a module is being attached to its parent assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f46cb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f46cb-104">Syntax</span></span>  
  
```  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f46cb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f46cb-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="f46cb-106">[in] Die ID des Moduls, die angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="f46cb-106">[in] The ID of the module that is being attached.</span></span>  
  
 `AssemblyId`  
 <span data-ttu-id="f46cb-107">[in] Die ID der übergeordneten Assembly, die das Modul zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="f46cb-107">[in] The ID of the parent assembly to which the module is attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f46cb-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f46cb-108">Remarks</span></span>  
 <span data-ttu-id="f46cb-109">Ein Modul kann durch eine Importadresstabelle (IAT), geladen werden, durch einen Aufruf von `LoadLibrary`, oder über einen Metadatenverweis.</span><span class="sxs-lookup"><span data-stu-id="f46cb-109">A module can be loaded through an import address table (IAT), through a call to `LoadLibrary`, or through a metadata reference.</span></span> <span data-ttu-id="f46cb-110">Daher hat das common Language Runtime (CLR)-Ladeprogramm mehrere Codepfade zur Bestimmung der Assembly, in der ein Modul befindet.</span><span class="sxs-lookup"><span data-stu-id="f46cb-110">As a result, the common language runtime (CLR) loader has multiple code paths for determining the assembly in which a module lives.</span></span> <span data-ttu-id="f46cb-111">Daher ist es möglich, dass Sie nach [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) aufgerufen wird, wird das Modul ist nicht bekannt, welche Assembly ist, und die übergeordnete Assembly-ID ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="f46cb-111">Therefore, it is possible that after [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) is called, the module does not know what assembly it is in and getting the parent assembly ID is not possible.</span></span> <span data-ttu-id="f46cb-112">Die `ModuleAttachedToAssembly` Methode wird aufgerufen, wenn das Modul, um die übergeordnete Assembly und die übergeordnete Assembly angefügt wird-ID abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="f46cb-112">The `ModuleAttachedToAssembly` method is called when the module is attached to its parent assembly and its parent assembly ID can be obtained.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f46cb-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f46cb-113">Requirements</span></span>  
 <span data-ttu-id="f46cb-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f46cb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f46cb-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f46cb-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f46cb-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f46cb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f46cb-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f46cb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f46cb-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f46cb-118">See also</span></span>

- [<span data-ttu-id="f46cb-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f46cb-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
