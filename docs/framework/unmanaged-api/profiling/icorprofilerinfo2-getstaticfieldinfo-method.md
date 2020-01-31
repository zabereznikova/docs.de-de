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
ms.openlocfilehash: d30d0bc262d76cf8980f90d8384173d89baf92d5
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862684"
---
# <a name="icorprofilerinfo2getstaticfieldinfo-method"></a><span data-ttu-id="14013-102">ICorProfilerInfo2::GetStaticFieldInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="14013-102">ICorProfilerInfo2::GetStaticFieldInfo Method</span></span>
<span data-ttu-id="14013-103">Ruft einen Wert ab, der die Art der statischen angibt, die für das angegebene Feld gilt.</span><span class="sxs-lookup"><span data-stu-id="14013-103">Gets a value that indicates the kind of static that applies to the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14013-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="14013-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldInfo (  
    [in] ClassID               classId,  
    [in] mdFieldDef            fieldToken,  
    [out] COR_PRF_STATIC_TYPE  *pFieldInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14013-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="14013-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="14013-106">in Die ID der Klasse, in der das statische Feld definiert ist.</span><span class="sxs-lookup"><span data-stu-id="14013-106">[in] The ID of the class in which the static field is defined.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="14013-107">in Das Metadatentoken für das statische Feld.</span><span class="sxs-lookup"><span data-stu-id="14013-107">[in] The metadata token for the static field.</span></span>  
  
 `pFieldInfo`  
 <span data-ttu-id="14013-108">vorgenommen Ein Zeiger auf einen Wert der [COR_PRF_STATIC_TYPE](cor-prf-static-type-enumeration.md) Enumeration, der angibt, ob das angegebene Feld statisch ist, und wenn dies der Fall ist, die Art der statischen, die für das Feld gilt.</span><span class="sxs-lookup"><span data-stu-id="14013-108">[out] A pointer to a value of the [COR_PRF_STATIC_TYPE](cor-prf-static-type-enumeration.md) enumeration that indicates whether the specified field is static, and if so, the kind of static that applies to the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14013-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="14013-109">Remarks</span></span>  
 <span data-ttu-id="14013-110">Diese Informationen können verwendet werden, um zu bestimmen, welche Funktion aufgerufen werden soll, um die Adresse des statischen Felds abzurufen.</span><span class="sxs-lookup"><span data-stu-id="14013-110">This information can be used to determine which function to call to get the address of the static field.</span></span>  
  
 <span data-ttu-id="14013-111">Der Profiler-Code sollte weiterhin die Metadaten für ein statisches Feld überprüfen, um sicherzustellen, dass es tatsächlich über eine Adresse verfügt.</span><span class="sxs-lookup"><span data-stu-id="14013-111">The profiler code should still check the metadata for a static field to ensure that it actually has an address.</span></span> <span data-ttu-id="14013-112">Statische Literale (d. h. Konstanten) sind nur in den Metadaten vorhanden und verfügen nicht über eine Adresse.</span><span class="sxs-lookup"><span data-stu-id="14013-112">Static literals (that is, constants) exist only in the metadata and do not have an address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14013-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="14013-113">Requirements</span></span>  
 <span data-ttu-id="14013-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14013-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14013-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="14013-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="14013-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14013-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14013-117">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14013-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14013-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14013-118">See also</span></span>

- [<span data-ttu-id="14013-119">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="14013-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="14013-120">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="14013-120">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
