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
ms.openlocfilehash: a5573765486112a83f5ea7cc9258447692f72166
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864065"
---
# <a name="icorprofilerinfogetclassfromobject-method"></a><span data-ttu-id="35c5a-102">ICorProfilerInfo::GetClassFromObject-Methode</span><span class="sxs-lookup"><span data-stu-id="35c5a-102">ICorProfilerInfo::GetClassFromObject Method</span></span>
<span data-ttu-id="35c5a-103">Ruft den `ClassID` eines-Objekts ab, wenn dessen `ObjectID`.</span><span class="sxs-lookup"><span data-stu-id="35c5a-103">Gets the `ClassID` of an object, given its `ObjectID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35c5a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="35c5a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35c5a-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="35c5a-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="35c5a-106">in Die ID des Objekts, für das die `ClassID`erhalten werden soll.</span><span class="sxs-lookup"><span data-stu-id="35c5a-106">[in] The ID of the object for which to get the `ClassID`.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="35c5a-107">vorgenommen Ein Zeiger auf den zurückgegebenen `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="35c5a-107">[out] A pointer to the returned `ClassID`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35c5a-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="35c5a-108">Remarks</span></span>  
 <span data-ttu-id="35c5a-109">Ein NULL-`pClassId` gibt an, dass `objectId` einen Typ aufweist, der entladen wird.</span><span class="sxs-lookup"><span data-stu-id="35c5a-109">A null `pClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35c5a-110">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="35c5a-110">Requirements</span></span>  
 <span data-ttu-id="35c5a-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35c5a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35c5a-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="35c5a-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="35c5a-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35c5a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35c5a-114">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35c5a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35c5a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35c5a-115">See also</span></span>

- [<span data-ttu-id="35c5a-116">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="35c5a-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
