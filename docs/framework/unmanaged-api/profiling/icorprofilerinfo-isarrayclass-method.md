---
title: ICorProfilerInfo::IsArrayClass-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.IsArrayClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::IsArrayClass
helpviewer_keywords:
- IsArrayClass method [.NET Framework profiling]
- ICorProfilerInfo::IsArrayClass method [.NET Framework profiling]
ms.assetid: 7f230961-23a6-4d56-ad2d-7a876d65705f
topic_type:
- apiref
ms.openlocfilehash: 2608f91a7c5baa935e48fbe58ad4d14aaaad1f0d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722504"
---
# <a name="icorprofilerinfoisarrayclass-method"></a><span data-ttu-id="7134c-102">ICorProfilerInfo::IsArrayClass-Methode</span><span class="sxs-lookup"><span data-stu-id="7134c-102">ICorProfilerInfo::IsArrayClass Method</span></span>

<span data-ttu-id="7134c-103">Bestimmt, ob die angegebene Klasse eine Array Klasse ist.</span><span class="sxs-lookup"><span data-stu-id="7134c-103">Determines whether the specified class is an array class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7134c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7134c-104">Syntax</span></span>  
  
```cpp  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7134c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7134c-105">Parameters</span></span>  

 `classId`  
 <span data-ttu-id="7134c-106">in Die ID der zu überprüfenden Klasse.</span><span class="sxs-lookup"><span data-stu-id="7134c-106">[in] The ID of the class to be examined.</span></span>  
  
 `pBaseElemType`  
 <span data-ttu-id="7134c-107">vorgenommen Ein Zeiger auf einen Wert der CorElementType-Enumeration, der den Typ der Array Elemente angibt.</span><span class="sxs-lookup"><span data-stu-id="7134c-107">[out] A pointer to a value of the CorElementType enumeration that indicates the type of the array elements.</span></span>  
  
 `pBaseClassId`  
 <span data-ttu-id="7134c-108">vorgenommen Ein Zeiger auf die Klassen-ID der Array Elemente (falls verfügbar).</span><span class="sxs-lookup"><span data-stu-id="7134c-108">[out] A pointer to the class ID of the array elements, when available.</span></span>  
  
 `pcRank`  
 <span data-ttu-id="7134c-109">vorgenommen Ein Zeiger auf eine ganze Zahl, die den Rang (d. h. die Anzahl der Dimensionen) des Arrays angibt.</span><span class="sxs-lookup"><span data-stu-id="7134c-109">[out] A pointer to an integer that indicates the rank (that is, number of dimensions) of the array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7134c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7134c-110">Remarks</span></span>  

 <span data-ttu-id="7134c-111">Wenn die angegebene Klasse eine Array Klasse ist, `IsArrayClass` gibt die Methode eine S_OK HRESULT und Werte für alle Ausgabeparameter ungleich NULL zurück.</span><span class="sxs-lookup"><span data-stu-id="7134c-111">If the specified class is an array class, the `IsArrayClass` method returns an S_OK HRESULT and values for any non-null output parameters.</span></span> <span data-ttu-id="7134c-112">Andernfalls wird S_FALSE zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7134c-112">Otherwise, it returns S_FALSE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7134c-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7134c-113">Requirements</span></span>  

 <span data-ttu-id="7134c-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7134c-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7134c-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7134c-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7134c-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7134c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7134c-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7134c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7134c-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7134c-118">See also</span></span>

- [<span data-ttu-id="7134c-119">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7134c-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
