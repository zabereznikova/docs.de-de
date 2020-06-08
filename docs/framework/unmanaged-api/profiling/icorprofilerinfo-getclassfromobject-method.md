---
title: ICorProfilerInfo::GetClassFromObject-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromObject
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromObject
helpviewer_keywords:
- GetClassFromObject method [.NET Framework profiling]
- ICorProfilerInfo::GetClassFromObject method [.NET Framework profiling]
ms.assetid: b97493fb-713e-49d5-a73e-5688b2ad0700
topic_type:
- apiref
ms.openlocfilehash: 613267549329d2f48dcd18ae341e47538e414ac0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498530"
---
# <a name="icorprofilerinfogetclassfromobject-method"></a><span data-ttu-id="22e78-102">ICorProfilerInfo::GetClassFromObject-Methode</span><span class="sxs-lookup"><span data-stu-id="22e78-102">ICorProfilerInfo::GetClassFromObject Method</span></span>
<span data-ttu-id="22e78-103">Ruft das- `ClassID` Objekt eines-Objekts ab, wenn sein `ObjectID` .</span><span class="sxs-lookup"><span data-stu-id="22e78-103">Gets the `ClassID` of an object, given its `ObjectID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22e78-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="22e78-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22e78-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="22e78-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="22e78-106">in Die ID des Objekts, für das die-Objekt-ID zu erhalten ist `ClassID` .</span><span class="sxs-lookup"><span data-stu-id="22e78-106">[in] The ID of the object for which to get the `ClassID`.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="22e78-107">vorgenommen Ein Zeiger auf die zurückgegebene `ClassID` .</span><span class="sxs-lookup"><span data-stu-id="22e78-107">[out] A pointer to the returned `ClassID`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22e78-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="22e78-108">Remarks</span></span>  
 <span data-ttu-id="22e78-109">Ein NULL-Wert `pClassId` gibt an, dass `objectId` einen Typ aufweist, der entladen wird.</span><span class="sxs-lookup"><span data-stu-id="22e78-109">A null `pClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22e78-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="22e78-110">Requirements</span></span>  
 <span data-ttu-id="22e78-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22e78-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22e78-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="22e78-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="22e78-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22e78-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22e78-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22e78-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22e78-115">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="22e78-115">See also</span></span>

- [<span data-ttu-id="22e78-116">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22e78-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
