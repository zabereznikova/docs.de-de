---
title: ICorProfilerInfo::SetILFunctionBody-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.SetILFunctionBody
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerInfo::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method [.NET Framework profiling]
ms.assetid: b159c712-00f4-4fc7-a990-40bf9f642e8f
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c44fa89ba66a306792f1ffed162447a6305a0347
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfosetilfunctionbody-method"></a><span data-ttu-id="8f73a-102">ICorProfilerInfo::SetILFunctionBody-Methode</span><span class="sxs-lookup"><span data-stu-id="8f73a-102">ICorProfilerInfo::SetILFunctionBody Method</span></span>
<span data-ttu-id="8f73a-103">Ersetzt den Text der angegebenen Funktion im angegebenen Modul.</span><span class="sxs-lookup"><span data-stu-id="8f73a-103">Replaces the body of the specified function in the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f73a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f73a-104">Syntax</span></span>  
  
```  
HRESULT SetILFunctionBody(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodid,  
    [in] LPCBYTE     pbNewILMethodHeader);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8f73a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8f73a-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="8f73a-106">[in] Die ID des Moduls, in dem die Funktion befindet.</span><span class="sxs-lookup"><span data-stu-id="8f73a-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodid`  
 <span data-ttu-id="8f73a-107">[in] Das Token der Funktion, für die den Text ersetzt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8f73a-107">[in] The token of the function for which to replace the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="8f73a-108">[in] Der neue Header für die Funktion.</span><span class="sxs-lookup"><span data-stu-id="8f73a-108">[in] The new header for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f73a-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8f73a-109">Remarks</span></span>  
 <span data-ttu-id="8f73a-110">Die `SetILFunctionBody` -Methode ersetzt die relative virtuelle Adresse der Funktion in den Metadaten, sodass er auf den Hauptteil der neuen Funktion verweist und alle internen Datenstrukturen nach Bedarf passt.</span><span class="sxs-lookup"><span data-stu-id="8f73a-110">The `SetILFunctionBody` method replaces the relative virtual address of the function in the metadata so that it points to the new function body, and adjusts any internal data structures as required.</span></span>  
  
 <span data-ttu-id="8f73a-111">Die `SetILFunctionBody` Methode kann aufgerufen werden, nur für Funktionen, die nie von einem Just-in-Time (JIT)-Compiler kompiliert wurden.</span><span class="sxs-lookup"><span data-stu-id="8f73a-111">The `SetILFunctionBody` method can be called on only those functions that have never been compiled by a just-in-time (JIT) compiler.</span></span>  
  
 <span data-ttu-id="8f73a-112">Verwenden der [ICorProfilerInfo:: GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md) Methode, um Speicherplatz für die neue Methode, um sicherzustellen, dass der Puffer kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="8f73a-112">Use the [ICorProfilerInfo::GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md) method to allocate space for the new method to ensure that the buffer is compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f73a-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8f73a-113">Requirements</span></span>  
 <span data-ttu-id="8f73a-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f73a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f73a-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8f73a-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8f73a-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f73a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f73a-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f73a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f73a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f73a-118">See Also</span></span>  
 [<span data-ttu-id="8f73a-119">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8f73a-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
