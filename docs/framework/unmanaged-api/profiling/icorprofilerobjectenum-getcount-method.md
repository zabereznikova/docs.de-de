---
title: ICorProfilerObjectEnum::GetCount-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.GetCount
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::GetCount
helpviewer_keywords:
- ICorProfilerObjectEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: 166b0761-ed80-4ccd-9973-dc20e61bf8fa
topic_type:
- apiref
ms.openlocfilehash: 4c867a9e263f022fc6f8d90a883562e2560ad1b2
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494656"
---
# <a name="icorprofilerobjectenumgetcount-method"></a><span data-ttu-id="a19d0-102">ICorProfilerObjectEnum::GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="a19d0-102">ICorProfilerObjectEnum::GetCount Method</span></span>
<span data-ttu-id="a19d0-103">Ruft die Gesamtanzahl der fixierten Objekte in der Auflistung ab.</span><span class="sxs-lookup"><span data-stu-id="a19d0-103">Gets the total number of frozen objects in the collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a19d0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a19d0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a19d0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a19d0-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="a19d0-106">vorgenommen Ein Zeiger auf die Anzahl der fixierten Objekte in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="a19d0-106">[out] A pointer to the number of frozen objects in the collection.</span></span>  
  
 <span data-ttu-id="a19d0-107">Diese Methode gibt immer 0 (null) in der .NET Framework Version 3,5 Service Pack 1 (SP1) und höheren Versionen zurück.</span><span class="sxs-lookup"><span data-stu-id="a19d0-107">This method will always return zero in the .NET Framework version 3.5 Service Pack 1 (SP1) and later versions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a19d0-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a19d0-108">Requirements</span></span>  
 <span data-ttu-id="a19d0-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a19d0-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a19d0-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a19d0-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a19d0-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a19d0-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a19d0-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a19d0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a19d0-113">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="a19d0-113">See also</span></span>

- [<span data-ttu-id="a19d0-114">ICorProfilerObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a19d0-114">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
