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
ms.openlocfilehash: fe4f3a7355339c9b5adbe5de062f0a5688d81c23
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727184"
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a><span data-ttu-id="7c7d1-102">ICorProfilerInfo2::EnumModuleFrozenObjects-Methode</span><span class="sxs-lookup"><span data-stu-id="7c7d1-102">ICorProfilerInfo2::EnumModuleFrozenObjects Method</span></span>

<span data-ttu-id="7c7d1-103">Ruft einen Enumerator ab, der die iterierung der fixierten Objekte im angegebenen Modul zulässt. Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="7c7d1-103">Gets an enumerator that allows iteration over the frozen objects in the specified module.This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c7d1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7c7d1-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c7d1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7c7d1-105">Parameters</span></span>  

 `moduleID`  
 <span data-ttu-id="7c7d1-106">in Die ID des Moduls, das die aufzuzählenden fixierten Objekte enthält.</span><span class="sxs-lookup"><span data-stu-id="7c7d1-106">[in] The ID of the module that contains the frozen objects to be enumerated.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="7c7d1-107">vorgenommen Ein Zeiger auf die Adresse einer [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) -Schnittstelle, die die fixierten Objekte auflistet.</span><span class="sxs-lookup"><span data-stu-id="7c7d1-107">[out] A pointer to the address of an [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) interface, which enumerates the frozen objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c7d1-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7c7d1-108">Requirements</span></span>  

 <span data-ttu-id="7c7d1-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c7d1-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c7d1-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7c7d1-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7c7d1-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c7d1-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c7d1-112">**.NET Framework Versionen:** 3,5, 3,0 SP1, 3,0, 2,0 SP1, 2,0</span><span class="sxs-lookup"><span data-stu-id="7c7d1-112">**.NET Framework Versions:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c7d1-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7c7d1-113">See also</span></span>

- [<span data-ttu-id="7c7d1-114">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c7d1-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="7c7d1-115">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c7d1-115">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
