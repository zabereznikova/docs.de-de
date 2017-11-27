---
title: ICorProfilerCallback::ModuleAttachedToAssembly-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ModuleAttachedToAssembly
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ModuleAttachedToAssembly
helpviewer_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly method [.NET Framework profiling]
- ModuleAttachedToAssembly method [.NET Framework profiling]
ms.assetid: b595798a-5d40-4cac-ab4f-911c61d2c5d2
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2c285a42bb48970756a54d5313d2839c76a9835c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a><span data-ttu-id="801d3-102">ICorProfilerCallback::ModuleAttachedToAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="801d3-102">ICorProfilerCallback::ModuleAttachedToAssembly Method</span></span>
<span data-ttu-id="801d3-103">Benachrichtigt den Profiler, dass ein Modul an seine übergeordnete Assembly verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="801d3-103">Notifies the profiler that a module is being attached to its parent assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="801d3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="801d3-104">Syntax</span></span>  
  
```  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="801d3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="801d3-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="801d3-106">[in] Die ID des Moduls, die angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="801d3-106">[in] The ID of the module that is being attached.</span></span>  
  
 `AssemblyId`  
 <span data-ttu-id="801d3-107">[in] Die ID der übergeordneten Assembly, die das Modul angeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="801d3-107">[in] The ID of the parent assembly to which the module is attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="801d3-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="801d3-108">Remarks</span></span>  
 <span data-ttu-id="801d3-109">Ein Modul kann durch eine Importadresstabelle (IAT), geladen werden, durch einen Aufruf von `LoadLibrary`, oder durch einen Metadatenverweis.</span><span class="sxs-lookup"><span data-stu-id="801d3-109">A module can be loaded through an import address table (IAT), through a call to `LoadLibrary`, or through a metadata reference.</span></span> <span data-ttu-id="801d3-110">Folglich weist das common Language Runtime (CLR)-Ladeprogramm mehrere Codepfade zur Bestimmung der Assembly, in der ein Modul aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="801d3-110">As a result, the common language runtime (CLR) loader has multiple code paths for determining the assembly in which a module lives.</span></span> <span data-ttu-id="801d3-111">Daher ist es möglich, dass nach dem [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) aufgerufen wird, wird das Modul weiß nicht, welche Assembly befindet sich im und Abrufen der übergeordneten Assembly-ID ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="801d3-111">Therefore, it is possible that after [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) is called, the module does not know what assembly it is in and getting the parent assembly ID is not possible.</span></span> <span data-ttu-id="801d3-112">Die `ModuleAttachedToAssembly` Methode wird aufgerufen, wenn das Modul, um die übergeordnete Assembly und der übergeordneten Assembly angeschlossen ist-ID abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="801d3-112">The `ModuleAttachedToAssembly` method is called when the module is attached to its parent assembly and its parent assembly ID can be obtained.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="801d3-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="801d3-113">Requirements</span></span>  
 <span data-ttu-id="801d3-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="801d3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="801d3-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="801d3-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="801d3-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="801d3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="801d3-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="801d3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="801d3-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="801d3-118">See Also</span></span>  
 [<span data-ttu-id="801d3-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="801d3-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
