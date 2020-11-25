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
ms.openlocfilehash: 4abcf9f4575b32dd125fd8a00783043900993c3e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724103"
---
# <a name="icorprofilerinfogetobjectsize-method"></a><span data-ttu-id="f30a9-102">ICorProfilerInfo::GetObjectSize-Methode</span><span class="sxs-lookup"><span data-stu-id="f30a9-102">ICorProfilerInfo::GetObjectSize Method</span></span>

<span data-ttu-id="f30a9-103">Ruft die Größe eines angegebenen-Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="f30a9-103">Gets the size of a specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f30a9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f30a9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f30a9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f30a9-105">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="f30a9-106">in Die ID des Objekts.</span><span class="sxs-lookup"><span data-stu-id="f30a9-106">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="f30a9-107">vorgenommen Ein Zeiger auf die Größe des-Objekts in Bytes.</span><span class="sxs-lookup"><span data-stu-id="f30a9-107">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f30a9-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f30a9-108">Remarks</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f30a9-109">Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="f30a9-109">This method is obsolete.</span></span> <span data-ttu-id="f30a9-110">Er gibt COR_E_OVERFLOW für Objekte zurück, die größer als 4 GB auf 64-Bit-Plattformen sind.</span><span class="sxs-lookup"><span data-stu-id="f30a9-110">It returns COR_E_OVERFLOW for objects greater than 4GB on 64-bit platforms.</span></span> <span data-ttu-id="f30a9-111">Verwenden Sie stattdessen die  [ICorProfilerInfo4:: GetObjectSize2](icorprofilerinfo4-getobjectsize2-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="f30a9-111">Use the  [ICorProfilerInfo4::GetObjectSize2](icorprofilerinfo4-getobjectsize2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="f30a9-112">Unterschiedliche Objekte der gleichen Typen haben oft dieselbe Größe.</span><span class="sxs-lookup"><span data-stu-id="f30a9-112">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="f30a9-113">Einige Typen, z. b. Arrays oder Zeichen folgen, können jedoch für jedes Objekt eine andere Größe aufweisen.</span><span class="sxs-lookup"><span data-stu-id="f30a9-113">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
 <span data-ttu-id="f30a9-114">Die von der-Methode zurückgegebene Größe `GetObjectSize` schließt keine Ausrichtungs Auffüll Zeichen ein, die möglicherweise angezeigt werden, nachdem sich das-Objekt auf dem Garbage Collection Heap befindet.</span><span class="sxs-lookup"><span data-stu-id="f30a9-114">The size returned by the `GetObjectSize` method does not include any alignment padding that may appear after the object is on the garbage collection heap.</span></span> <span data-ttu-id="f30a9-115">Wenn Sie die- `GetObjectSize` Methode verwenden, um vom Objekt auf das Objekt im Garbage Collection Heap zu verschieben, fügen Sie ggf. manuell die Ausrichtung der Ausrichtungs Abstände hinzu.</span><span class="sxs-lookup"><span data-stu-id="f30a9-115">If you use the `GetObjectSize` method to advance from object to object on the garbage collection heap, add alignment padding manually, as necessary.</span></span>  
  
- <span data-ttu-id="f30a9-116">Bei 32-Bit-Fenstern verwenden COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1 und COR_PRF_GC_GEN_2 4-Byte-Ausrichtung, und COR_PRF_GC_LARGE_OBJECT_HEAP verwendet 8-Byte-Ausrichtung.</span><span class="sxs-lookup"><span data-stu-id="f30a9-116">On 32-bit Windows, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1, and COR_PRF_GC_GEN_2 use 4-byte alignment, and COR_PRF_GC_LARGE_OBJECT_HEAP uses 8-byte alignment.</span></span>  
  
- <span data-ttu-id="f30a9-117">Bei 64-Bit-Fenstern ist die Ausrichtung immer 8 Bytes.</span><span class="sxs-lookup"><span data-stu-id="f30a9-117">On 64-bit Windows, the alignment is always 8 bytes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f30a9-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f30a9-118">Requirements</span></span>  

 <span data-ttu-id="f30a9-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f30a9-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f30a9-120">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f30a9-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f30a9-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f30a9-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f30a9-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f30a9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f30a9-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f30a9-123">See also</span></span>

- [<span data-ttu-id="f30a9-124">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f30a9-124">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
