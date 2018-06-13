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
ms.openlocfilehash: 77b07dae5b53db58b3628f677be1714e66ac18ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455256"
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a><span data-ttu-id="5cf26-102">ICorProfilerInfo2::EnumModuleFrozenObjects-Methode</span><span class="sxs-lookup"><span data-stu-id="5cf26-102">ICorProfilerInfo2::EnumModuleFrozenObjects Method</span></span>
<span data-ttu-id="5cf26-103">Gibt einen Enumerator zurück, der Iteration der fixierten Objekte im angegebenen Modul ermöglicht. Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="5cf26-103">Gets an enumerator that allows iteration over the frozen objects in the specified module.This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cf26-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5cf26-104">Syntax</span></span>  
  
```  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5cf26-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5cf26-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="5cf26-106">[in] Die ID des Moduls, enthält die fixierten Objekte aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5cf26-106">[in] The ID of the module that contains the frozen objects to be enumerated.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="5cf26-107">[out] Ein Zeiger auf die Adresse des ein [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) -Schnittstelle, die die fixierten Objekte auflistet.</span><span class="sxs-lookup"><span data-stu-id="5cf26-107">[out] A pointer to the address of an [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface, which enumerates the frozen objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cf26-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5cf26-108">Requirements</span></span>  
 <span data-ttu-id="5cf26-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5cf26-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cf26-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5cf26-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5cf26-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5cf26-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5cf26-112">**.NET Framework-Versionen:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span><span class="sxs-lookup"><span data-stu-id="5cf26-112">**.NET Framework Versions:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cf26-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5cf26-113">See Also</span></span>  
 [<span data-ttu-id="5cf26-114">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5cf26-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="5cf26-115">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5cf26-115">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
