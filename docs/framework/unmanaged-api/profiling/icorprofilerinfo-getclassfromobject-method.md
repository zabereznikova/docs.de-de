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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 81afb9b40269b04a59c54636c7e88c1f67189593
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041712"
---
# <a name="icorprofilerinfogetclassfromobject-method"></a><span data-ttu-id="8f75f-102">ICorProfilerInfo::GetClassFromObject-Methode</span><span class="sxs-lookup"><span data-stu-id="8f75f-102">ICorProfilerInfo::GetClassFromObject Method</span></span>
<span data-ttu-id="8f75f-103">Ruft die `ClassID` eines angegebenen Objekts an, dessen `ObjectID`.</span><span class="sxs-lookup"><span data-stu-id="8f75f-103">Gets the `ClassID` of an object, given its `ObjectID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f75f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f75f-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f75f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8f75f-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="8f75f-106">[in] Die ID des Objekts, für das Abrufen der `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="8f75f-106">[in] The ID of the object for which to get the `ClassID`.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="8f75f-107">[out] Ein Zeiger auf das zurückgegebene `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="8f75f-107">[out] A pointer to the returned `ClassID`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f75f-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8f75f-108">Remarks</span></span>  
 <span data-ttu-id="8f75f-109">Ein NULL-Wert `pClassId` gibt an, dass `objectId` verfügt über einen Typ, der entladen wird.</span><span class="sxs-lookup"><span data-stu-id="8f75f-109">A null `pClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f75f-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8f75f-110">Requirements</span></span>  
 <span data-ttu-id="8f75f-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f75f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f75f-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8f75f-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8f75f-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f75f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f75f-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f75f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f75f-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f75f-115">See also</span></span>

- [<span data-ttu-id="8f75f-116">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8f75f-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
