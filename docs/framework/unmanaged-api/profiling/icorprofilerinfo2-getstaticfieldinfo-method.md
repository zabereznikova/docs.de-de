---
title: ICorProfilerInfo2::GetStaticFieldInfo-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStaticFieldInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo method [.NET Framework profiling]
- GetStaticFieldInfo method [.NET Framework profiling]
ms.assetid: fc663e76-e23f-49a8-bdd5-52cdf1a3b2b3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 36cb8d5865cdc4c1c8e34671010ede25d531bacf
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782258"
---
# <a name="icorprofilerinfo2getstaticfieldinfo-method"></a><span data-ttu-id="6b85a-102">ICorProfilerInfo2::GetStaticFieldInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="6b85a-102">ICorProfilerInfo2::GetStaticFieldInfo Method</span></span>
<span data-ttu-id="6b85a-103">Ruft einen Wert, der die Art der statischen angibt, die für das angegebene Feld gilt.</span><span class="sxs-lookup"><span data-stu-id="6b85a-103">Gets a value that indicates the kind of static that applies to the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b85a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b85a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldInfo (  
    [in] ClassID               classId,  
    [in] mdFieldDef            fieldToken,  
    [out] COR_PRF_STATIC_TYPE  *pFieldInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b85a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6b85a-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="6b85a-106">[in] Die ID der Klasse, in der das statische Feld definiert wird.</span><span class="sxs-lookup"><span data-stu-id="6b85a-106">[in] The ID of the class in which the static field is defined.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="6b85a-107">[in] Das Metadatentoken für das statische Feld.</span><span class="sxs-lookup"><span data-stu-id="6b85a-107">[in] The metadata token for the static field.</span></span>  
  
 `pFieldInfo`  
 <span data-ttu-id="6b85a-108">[out] Ein Zeiger auf den Wert der [COR_PRF_STATIC_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md) Enumeration, der angibt, ob das angegebene Feld statisch ist, und daher die Art der statischen, die auf das Feld gilt.</span><span class="sxs-lookup"><span data-stu-id="6b85a-108">[out] A pointer to a value of the [COR_PRF_STATIC_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md) enumeration that indicates whether the specified field is static, and if so, the kind of static that applies to the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b85a-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6b85a-109">Remarks</span></span>  
 <span data-ttu-id="6b85a-110">Diese Informationen kann verwendet werden, um zu bestimmen, welche Funktion aufgerufen wird, um die Adresse des statischen Felds abzurufen.</span><span class="sxs-lookup"><span data-stu-id="6b85a-110">This information can be used to determine which function to call to get the address of the static field.</span></span>  
  
 <span data-ttu-id="6b85a-111">Der Profilercode sollten überprüfen, die Metadaten für ein statisches Feld, um sicherzustellen, dass es sich tatsächlich um eine Adresse hat.</span><span class="sxs-lookup"><span data-stu-id="6b85a-111">The profiler code should still check the metadata for a static field to ensure that it actually has an address.</span></span> <span data-ttu-id="6b85a-112">Statische Literale (d. h. Konstanten) nur in den Metadaten vorhanden sein und müssen sich nicht auf eine Adresse.</span><span class="sxs-lookup"><span data-stu-id="6b85a-112">Static literals (that is, constants) exist only in the metadata and do not have an address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b85a-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6b85a-113">Requirements</span></span>  
 <span data-ttu-id="6b85a-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b85a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b85a-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6b85a-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6b85a-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b85a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b85a-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b85a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b85a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b85a-118">See also</span></span>

- [<span data-ttu-id="6b85a-119">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6b85a-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="6b85a-120">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6b85a-120">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
