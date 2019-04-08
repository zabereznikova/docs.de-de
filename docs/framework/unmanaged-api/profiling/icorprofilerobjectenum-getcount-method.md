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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8466de39f2f2769fec332290c187ecba396d7d56
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080929"
---
# <a name="icorprofilerobjectenumgetcount-method"></a><span data-ttu-id="7ab4e-102">ICorProfilerObjectEnum::GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="7ab4e-102">ICorProfilerObjectEnum::GetCount Method</span></span>
<span data-ttu-id="7ab4e-103">Ruft die Gesamtanzahl von fixierten Objekten in der Auflistung ab.</span><span class="sxs-lookup"><span data-stu-id="7ab4e-103">Gets the total number of frozen objects in the collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ab4e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ab4e-104">Syntax</span></span>  
  
```  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ab4e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7ab4e-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="7ab4e-106">[out] Ein Zeiger auf die Anzahl der fixierten Objekte in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="7ab4e-106">[out] A pointer to the number of frozen objects in the collection.</span></span>  
  
 <span data-ttu-id="7ab4e-107">Diese Methode gibt immer 0 (null) in .NET Framework, Version 3.5 Service Pack 1 (SP1) und höher.</span><span class="sxs-lookup"><span data-stu-id="7ab4e-107">This method will always return zero in the .NET Framework version 3.5 Service Pack 1 (SP1) and later versions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ab4e-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7ab4e-108">Requirements</span></span>  
 <span data-ttu-id="7ab4e-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ab4e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ab4e-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7ab4e-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7ab4e-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ab4e-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="7ab4e-112">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="7ab4e-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7ab4e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ab4e-113">See also</span></span>

- [<span data-ttu-id="7ab4e-114">ICorProfilerObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ab4e-114">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
