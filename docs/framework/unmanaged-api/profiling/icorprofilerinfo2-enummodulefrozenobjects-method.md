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
ms.openlocfilehash: 27b3037459ac4f995e37515f6e96c28449c80a4f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862944"
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a><span data-ttu-id="6a23d-102">ICorProfilerInfo2::EnumModuleFrozenObjects-Methode</span><span class="sxs-lookup"><span data-stu-id="6a23d-102">ICorProfilerInfo2::EnumModuleFrozenObjects Method</span></span>
<span data-ttu-id="6a23d-103">Ruft einen Enumerator ab, der die iterierung der fixierten Objekte im angegebenen Modul zulässt. Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="6a23d-103">Gets an enumerator that allows iteration over the frozen objects in the specified module.This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a23d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6a23d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a23d-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="6a23d-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="6a23d-106">in Die ID des Moduls, das die aufzuzählenden fixierten Objekte enthält.</span><span class="sxs-lookup"><span data-stu-id="6a23d-106">[in] The ID of the module that contains the frozen objects to be enumerated.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="6a23d-107">vorgenommen Ein Zeiger auf die Adresse einer [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) -Schnittstelle, die die fixierten Objekte auflistet.</span><span class="sxs-lookup"><span data-stu-id="6a23d-107">[out] A pointer to the address of an [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) interface, which enumerates the frozen objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a23d-108">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6a23d-108">Requirements</span></span>  
 <span data-ttu-id="6a23d-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a23d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a23d-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6a23d-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6a23d-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a23d-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a23d-112">**.NET Framework Versionen:** 3,5, 3,0 SP1, 3,0, 2,0 SP1, 2,0</span><span class="sxs-lookup"><span data-stu-id="6a23d-112">**.NET Framework Versions:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a23d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a23d-113">See also</span></span>

- [<span data-ttu-id="6a23d-114">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6a23d-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="6a23d-115">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6a23d-115">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
