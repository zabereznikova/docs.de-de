---
title: ICorProfilerInfo2::EnumModuleFrozenObjects-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.EnumModuleFrozenObjects
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::EnumModuleFrozenObjects
helpviewer_keywords:
- EnumModuleFrozenObjects method [.NET Framework profiling]
- ICorProfilerInfo2::EnumModuleFrozenObjects method [.NET Framework profiling]
ms.assetid: 920b6483-7064-4d64-8613-fcc38ccf9b1e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a325c3e1aa9c08e00dc2cc38e3f7833fa9f99897
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472576"
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a><span data-ttu-id="caa20-102">ICorProfilerInfo2::EnumModuleFrozenObjects-Methode</span><span class="sxs-lookup"><span data-stu-id="caa20-102">ICorProfilerInfo2::EnumModuleFrozenObjects Method</span></span>
<span data-ttu-id="caa20-103">Ruft einen Enumerator, der Iteration der fixierten Objekte im angegebenen Modul ermöglicht. Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="caa20-103">Gets an enumerator that allows iteration over the frozen objects in the specified module.This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caa20-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="caa20-104">Syntax</span></span>  
  
```  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="caa20-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="caa20-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="caa20-106">[in] Die ID des Moduls, enthält die fixierten Objekte aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="caa20-106">[in] The ID of the module that contains the frozen objects to be enumerated.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="caa20-107">[out] Ein Zeiger auf die Adresse einer [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) -Schnittstelle, die der fixierten Objekte auflistet.</span><span class="sxs-lookup"><span data-stu-id="caa20-107">[out] A pointer to the address of an [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface, which enumerates the frozen objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="caa20-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="caa20-108">Requirements</span></span>  
 <span data-ttu-id="caa20-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="caa20-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="caa20-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="caa20-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="caa20-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="caa20-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="caa20-112">**.NET Framework-Versionen:** 3.5, 3.0 SP1 3.0 2.0 SP1, 2.0</span><span class="sxs-lookup"><span data-stu-id="caa20-112">**.NET Framework Versions:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caa20-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="caa20-113">See also</span></span>
- [<span data-ttu-id="caa20-114">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="caa20-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="caa20-115">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="caa20-115">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
