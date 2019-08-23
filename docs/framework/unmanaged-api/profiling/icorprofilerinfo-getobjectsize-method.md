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
ms.openlocfilehash: 2ad2092c902b137df0dfe108743ef4081ca5f04d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69948115"
---
# <a name="icorprofilerinfogetobjectsize-method"></a><span data-ttu-id="64946-102">ICorProfilerInfo::GetObjectSize-Methode</span><span class="sxs-lookup"><span data-stu-id="64946-102">ICorProfilerInfo::GetObjectSize Method</span></span>
<span data-ttu-id="64946-103">Ruft die Größe eines angegebenen-Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="64946-103">Gets the size of a specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64946-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="64946-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64946-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="64946-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="64946-106">in Die ID des Objekts.</span><span class="sxs-lookup"><span data-stu-id="64946-106">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="64946-107">vorgenommen Ein Zeiger auf die Größe des-Objekts in Bytes.</span><span class="sxs-lookup"><span data-stu-id="64946-107">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64946-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="64946-108">Remarks</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="64946-109">Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="64946-109">This method is obsolete.</span></span> <span data-ttu-id="64946-110">Sie gibt COR_E_OVERFLOW für Objekte, die größer als 4 GB sind, auf 64-Bit-Plattformen zurück.</span><span class="sxs-lookup"><span data-stu-id="64946-110">It returns COR_E_OVERFLOW for objects greater than 4GB on 64-bit platforms.</span></span> <span data-ttu-id="64946-111">Verwenden Sie stattdessen die [ICorProfilerInfo4:: GetObjectSize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="64946-111">Use the  [ICorProfilerInfo4::GetObjectSize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="64946-112">Unterschiedliche Objekte der gleichen Typen haben oft dieselbe Größe.</span><span class="sxs-lookup"><span data-stu-id="64946-112">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="64946-113">Einige Typen, z. b. Arrays oder Zeichen folgen, können jedoch für jedes Objekt eine andere Größe aufweisen.</span><span class="sxs-lookup"><span data-stu-id="64946-113">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
 <span data-ttu-id="64946-114">Die von der `GetObjectSize` -Methode zurückgegebene Größe schließt keine Ausrichtungs Auffüll Zeichen ein, die möglicherweise angezeigt werden, nachdem sich das-Objekt auf dem Garbage Collection Heap befindet.</span><span class="sxs-lookup"><span data-stu-id="64946-114">The size returned by the `GetObjectSize` method does not include any alignment padding that may appear after the object is on the garbage collection heap.</span></span> <span data-ttu-id="64946-115">Wenn Sie die- `GetObjectSize` Methode verwenden, um vom Objekt auf das Objekt im Garbage Collection Heap zu verschieben, fügen Sie ggf. manuell die Ausrichtung der Ausrichtungs Abstände hinzu.</span><span class="sxs-lookup"><span data-stu-id="64946-115">If you use the `GetObjectSize` method to advance from object to object on the garbage collection heap, add alignment padding manually, as necessary.</span></span>  
  
- <span data-ttu-id="64946-116">Auf 32-Bit-Windows, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1 und COR_PRF_GC_GEN_2 verwenden Sie die 4-Byte-Ausrichtung, und COR_PRF_GC_LARGE_OBJECT_HEAP verwendet 8-Byte-Ausrichtung.</span><span class="sxs-lookup"><span data-stu-id="64946-116">On 32-bit Windows, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1, and COR_PRF_GC_GEN_2 use 4-byte alignment, and COR_PRF_GC_LARGE_OBJECT_HEAP uses 8-byte alignment.</span></span>  
  
- <span data-ttu-id="64946-117">Bei 64-Bit-Fenstern ist die Ausrichtung immer 8 Bytes.</span><span class="sxs-lookup"><span data-stu-id="64946-117">On 64-bit Windows, the alignment is always 8 bytes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64946-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="64946-118">Requirements</span></span>  
 <span data-ttu-id="64946-119">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64946-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64946-120">**Header:** Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="64946-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="64946-121">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64946-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64946-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64946-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64946-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64946-123">See also</span></span>

- [<span data-ttu-id="64946-124">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="64946-124">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
