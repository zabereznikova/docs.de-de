---
title: ICorProfilerInfo::GetObjectSize-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetObjectSize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetObjectSize
helpviewer_keywords:
- GetObjectSize method [.NET Framework profiling]
- ICorProfilerInfo::GetObjectSize method [.NET Framework profiling]
ms.assetid: 9f02e763-73f7-42cb-a41c-f78499d9482c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e03a618144ca322d51337e84486a8f5051a3d2a7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568880"
---
# <a name="icorprofilerinfogetobjectsize-method"></a><span data-ttu-id="9f1c8-102">ICorProfilerInfo::GetObjectSize-Methode</span><span class="sxs-lookup"><span data-stu-id="9f1c8-102">ICorProfilerInfo::GetObjectSize Method</span></span>
<span data-ttu-id="9f1c8-103">Ruft die Größe eines angegebenen Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="9f1c8-103">Gets the size of a specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f1c8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9f1c8-104">Syntax</span></span>  
  
```  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9f1c8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9f1c8-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="9f1c8-106">[in] Die ID des Objekts.</span><span class="sxs-lookup"><span data-stu-id="9f1c8-106">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="9f1c8-107">[out] Ein Zeiger auf die Größe des Objekts, in Bytes.</span><span class="sxs-lookup"><span data-stu-id="9f1c8-107">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f1c8-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9f1c8-108">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9f1c8-109">Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="9f1c8-109">This method is obsolete.</span></span> <span data-ttu-id="9f1c8-110">Sie gibt COR_E_OVERFLOW für Objekte größer als 4GB auf 64-Bit-Plattformen.</span><span class="sxs-lookup"><span data-stu-id="9f1c8-110">It returns COR_E_OVERFLOW for objects greater than 4GB on 64-bit platforms.</span></span> <span data-ttu-id="9f1c8-111">Verwenden der [icorprofilerinfo4:: Getobjectsize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="9f1c8-111">Use the  [ICorProfilerInfo4::GetObjectSize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="9f1c8-112">Verschiedene Objekte der gleichen Typen verfügen häufig über die gleiche Größe.</span><span class="sxs-lookup"><span data-stu-id="9f1c8-112">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="9f1c8-113">Allerdings möglicherweise einiger Typen wie Arrays bzw. Zeichenfolgen, die eine andere Größe für jedes Objekt.</span><span class="sxs-lookup"><span data-stu-id="9f1c8-113">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
 <span data-ttu-id="9f1c8-114">Die Größe, die zurückgegeben werden, indem die `GetObjectSize` Methode umfasst keine Ausrichtungszeichenabstände, die angezeigt werden kann, nachdem das Objekt in die Garbage Collection-Heap befindet.</span><span class="sxs-lookup"><span data-stu-id="9f1c8-114">The size returned by the `GetObjectSize` method does not include any alignment padding that may appear after the object is on the garbage collection heap.</span></span> <span data-ttu-id="9f1c8-115">Bei Verwendung der `GetObjectSize` Methode aus einem Objekt zu einem anderen Objekt auf dem Garbage Collection-Heap, fahren Sie fort, hinzuzufügen, Ausrichtung, die nach Bedarf manuell auffüllen.</span><span class="sxs-lookup"><span data-stu-id="9f1c8-115">If you use the `GetObjectSize` method to advance from object to object on the garbage collection heap, add alignment padding manually, as necessary.</span></span>  
  
-   <span data-ttu-id="9f1c8-116">Klicken Sie auf 32-Bit-Windows COR_PRF_GC_GEN_0 COR_PRF_GC_GEN_1 und COR_PRF_GC_GEN_2 verwenden 4-Byte-Ausrichtung und COR_PRF_GC_LARGE_OBJECT_HEAP verwendet 8-Byte-Ausrichtung.</span><span class="sxs-lookup"><span data-stu-id="9f1c8-116">On 32-bit Windows, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1, and COR_PRF_GC_GEN_2 use 4-byte alignment, and COR_PRF_GC_LARGE_OBJECT_HEAP uses 8-byte alignment.</span></span>  
  
-   <span data-ttu-id="9f1c8-117">Auf 64-Bit-Windows ist die Ausrichtung immer 8 Bytes.</span><span class="sxs-lookup"><span data-stu-id="9f1c8-117">On 64-bit Windows, the alignment is always 8 bytes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f1c8-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9f1c8-118">Requirements</span></span>  
 <span data-ttu-id="9f1c8-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f1c8-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f1c8-120">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9f1c8-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9f1c8-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f1c8-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f1c8-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f1c8-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f1c8-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f1c8-123">See also</span></span>
- [<span data-ttu-id="9f1c8-124">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9f1c8-124">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
