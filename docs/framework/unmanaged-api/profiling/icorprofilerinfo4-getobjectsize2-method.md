---
title: ICorProfilerInfo4::GetObjectSize2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetObjectSize2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetObjectSize2
helpviewer_keywords:
- GetObjectSize2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetObjectSize2 method [.NET Framework profiling]
ms.assetid: 4a3e43ed-3ee3-4395-ab14-f78b903be13e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 15829e08a755b91ff91ca939b92a5a87bd377e8b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59176292"
---
# <a name="icorprofilerinfo4getobjectsize2-method"></a><span data-ttu-id="2f6c9-102">ICorProfilerInfo4::GetObjectSize2-Methode</span><span class="sxs-lookup"><span data-stu-id="2f6c9-102">ICorProfilerInfo4::GetObjectSize2 Method</span></span>
<span data-ttu-id="2f6c9-103">Gibt die Größe eines angegebenen Objekts zurück.</span><span class="sxs-lookup"><span data-stu-id="2f6c9-103">Returns the size of a specified object.</span></span> <span data-ttu-id="2f6c9-104">Ersetzt die [ICorProfilerInfo:: GetObjectSize](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md) Methode, indem Sie reporting Größen von Objekten, die größer als die, in ausgedrückt werden kann eine `ULONG`.</span><span class="sxs-lookup"><span data-stu-id="2f6c9-104">Replaces the [ICorProfilerInfo::GetObjectSize](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md) method by reporting sizes of objects that are larger than what can be expressed in a `ULONG`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f6c9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2f6c9-105">Syntax</span></span>  
  
```  
HRESULT GetObjectSize2(  
    [in]  ObjectID objectId,  
    [out] SIZE_T *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f6c9-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2f6c9-106">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="2f6c9-107">[in] Die ID des Objekts.</span><span class="sxs-lookup"><span data-stu-id="2f6c9-107">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="2f6c9-108">[out] Ein Zeiger auf die Größe des Objekts, in Bytes.</span><span class="sxs-lookup"><span data-stu-id="2f6c9-108">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f6c9-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2f6c9-109">Remarks</span></span>  
 <span data-ttu-id="2f6c9-110">Verschiedene Objekte der gleichen Typen verfügen häufig über die gleiche Größe.</span><span class="sxs-lookup"><span data-stu-id="2f6c9-110">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="2f6c9-111">Allerdings möglicherweise einiger Typen wie Arrays bzw. Zeichenfolgen, die eine andere Größe für jedes Objekt.</span><span class="sxs-lookup"><span data-stu-id="2f6c9-111">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f6c9-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2f6c9-112">Requirements</span></span>  
 <span data-ttu-id="2f6c9-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f6c9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f6c9-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2f6c9-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2f6c9-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f6c9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f6c9-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f6c9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f6c9-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f6c9-117">See also</span></span>

- [<span data-ttu-id="2f6c9-118">ICorProfilerInfo4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2f6c9-118">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
