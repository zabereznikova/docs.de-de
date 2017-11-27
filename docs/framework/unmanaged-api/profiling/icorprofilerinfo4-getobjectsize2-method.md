---
title: ICorProfilerInfo4::GetObjectSize2-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo4.GetObjectSize2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo4::GetObjectSize2
helpviewer_keywords:
- GetObjectSize2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetObjectSize2 method [.NET Framework profiling]
ms.assetid: 4a3e43ed-3ee3-4395-ab14-f78b903be13e
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4898157e6525d3b9da4cfade9862b88252df7b14
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfo4getobjectsize2-method"></a><span data-ttu-id="fcf74-102">ICorProfilerInfo4::GetObjectSize2-Methode</span><span class="sxs-lookup"><span data-stu-id="fcf74-102">ICorProfilerInfo4::GetObjectSize2 Method</span></span>
<span data-ttu-id="fcf74-103">Gibt die Größe eines angegebenen Objekts zurück.</span><span class="sxs-lookup"><span data-stu-id="fcf74-103">Returns the size of a specified object.</span></span> <span data-ttu-id="fcf74-104">Ersetzt die [ICorProfilerInfo:: GetObjectSize](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md) Methode, indem die Größen von Objekten, die größer als in ausgedrückt werden können reporting eine `ULONG`.</span><span class="sxs-lookup"><span data-stu-id="fcf74-104">Replaces the [ICorProfilerInfo::GetObjectSize](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md) method by reporting sizes of objects that are larger than what can be expressed in a `ULONG`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcf74-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fcf74-105">Syntax</span></span>  
  
```  
HRESULT GetObjectSize2(  
    [in]  ObjectID objectId,  
    [out] SIZE_T *pcSize);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fcf74-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="fcf74-106">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="fcf74-107">[in] Die ID des Objekts.</span><span class="sxs-lookup"><span data-stu-id="fcf74-107">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="fcf74-108">[out] Ein Zeiger auf die Größe des Objekts, in Bytes.</span><span class="sxs-lookup"><span data-stu-id="fcf74-108">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fcf74-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fcf74-109">Remarks</span></span>  
 <span data-ttu-id="fcf74-110">Unterschiedliche Objekte der gleichen Typen werden häufig dieselbe Größe aufweisen.</span><span class="sxs-lookup"><span data-stu-id="fcf74-110">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="fcf74-111">Jedoch möglicherweise einige Typen, z. B. Arrays oder Zeichenfolgen, die eine andere Größe für jedes Objekt.</span><span class="sxs-lookup"><span data-stu-id="fcf74-111">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcf74-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fcf74-112">Requirements</span></span>  
 <span data-ttu-id="fcf74-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcf74-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcf74-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fcf74-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fcf74-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fcf74-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fcf74-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcf74-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcf74-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fcf74-117">See Also</span></span>  
 [<span data-ttu-id="fcf74-118">ICorProfilerInfo4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fcf74-118">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
