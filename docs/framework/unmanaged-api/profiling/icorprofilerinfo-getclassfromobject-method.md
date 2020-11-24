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
ms.openlocfilehash: 5a7edc6045969861679d1b80c0563e99f48932cf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680247"
---
# <a name="icorprofilerinfogetclassfromobject-method"></a><span data-ttu-id="f61dc-102">ICorProfilerInfo::GetClassFromObject-Methode</span><span class="sxs-lookup"><span data-stu-id="f61dc-102">ICorProfilerInfo::GetClassFromObject Method</span></span>

<span data-ttu-id="f61dc-103">Ruft das- `ClassID` Objekt eines-Objekts ab, wenn sein `ObjectID` .</span><span class="sxs-lookup"><span data-stu-id="f61dc-103">Gets the `ClassID` of an object, given its `ObjectID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f61dc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f61dc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f61dc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f61dc-105">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="f61dc-106">in Die ID des Objekts, für das die-Objekt-ID zu erhalten ist `ClassID` .</span><span class="sxs-lookup"><span data-stu-id="f61dc-106">[in] The ID of the object for which to get the `ClassID`.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="f61dc-107">vorgenommen Ein Zeiger auf die zurückgegebene `ClassID` .</span><span class="sxs-lookup"><span data-stu-id="f61dc-107">[out] A pointer to the returned `ClassID`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f61dc-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f61dc-108">Remarks</span></span>  

 <span data-ttu-id="f61dc-109">Ein NULL-Wert `pClassId` gibt an, dass `objectId` einen Typ aufweist, der entladen wird.</span><span class="sxs-lookup"><span data-stu-id="f61dc-109">A null `pClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f61dc-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f61dc-110">Requirements</span></span>  

 <span data-ttu-id="f61dc-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f61dc-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f61dc-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f61dc-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f61dc-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f61dc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f61dc-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f61dc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f61dc-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f61dc-115">See also</span></span>

- [<span data-ttu-id="f61dc-116">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f61dc-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
