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
ms.openlocfilehash: 441f7743ba01884592393ce9382348fbecaeaa9d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861878"
---
# <a name="icorprofilerinfo4getobjectsize2-method"></a><span data-ttu-id="a7a9c-102">ICorProfilerInfo4::GetObjectSize2-Methode</span><span class="sxs-lookup"><span data-stu-id="a7a9c-102">ICorProfilerInfo4::GetObjectSize2 Method</span></span>
<span data-ttu-id="a7a9c-103">Gibt die Größe eines angegebenen-Objekts zurück.</span><span class="sxs-lookup"><span data-stu-id="a7a9c-103">Returns the size of a specified object.</span></span> <span data-ttu-id="a7a9c-104">Ersetzt die [ICorProfilerInfo:: GetObjectSize](icorprofilerinfo-getobjectsize-method.md) -Methode durch berichtsgrößen von Objekten, die größer sind als in einer `ULONG`ausgedrückt werden können.</span><span class="sxs-lookup"><span data-stu-id="a7a9c-104">Replaces the [ICorProfilerInfo::GetObjectSize](icorprofilerinfo-getobjectsize-method.md) method by reporting sizes of objects that are larger than what can be expressed in a `ULONG`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7a9c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7a9c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize2(  
    [in]  ObjectID objectId,  
    [out] SIZE_T *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7a9c-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="a7a9c-106">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="a7a9c-107">in Die ID des Objekts.</span><span class="sxs-lookup"><span data-stu-id="a7a9c-107">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="a7a9c-108">vorgenommen Ein Zeiger auf die Größe des-Objekts in Bytes.</span><span class="sxs-lookup"><span data-stu-id="a7a9c-108">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7a9c-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a7a9c-109">Remarks</span></span>  
 <span data-ttu-id="a7a9c-110">Unterschiedliche Objekte der gleichen Typen haben oft dieselbe Größe.</span><span class="sxs-lookup"><span data-stu-id="a7a9c-110">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="a7a9c-111">Einige Typen, z. b. Arrays oder Zeichen folgen, können jedoch für jedes Objekt eine andere Größe aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a7a9c-111">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7a9c-112">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a7a9c-112">Requirements</span></span>  
 <span data-ttu-id="a7a9c-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7a9c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7a9c-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a7a9c-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a7a9c-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7a9c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7a9c-116">**.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7a9c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7a9c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7a9c-117">See also</span></span>

- [<span data-ttu-id="a7a9c-118">ICorProfilerInfo4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7a9c-118">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
