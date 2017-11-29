---
title: ICorProfilerObjectEnum::GetCount-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerObjectEnum.GetCount
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerObjectEnum::GetCount
helpviewer_keywords:
- ICorProfilerObjectEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: 166b0761-ed80-4ccd-9973-dc20e61bf8fa
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0680921a64d8f8bf9cdc5b4137c56dd8dfb7878e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerobjectenumgetcount-method"></a><span data-ttu-id="9a14c-102">ICorProfilerObjectEnum::GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="9a14c-102">ICorProfilerObjectEnum::GetCount Method</span></span>
<span data-ttu-id="9a14c-103">Ruft die Gesamtzahl der fixierten Objekte in der Auflistung ab.</span><span class="sxs-lookup"><span data-stu-id="9a14c-103">Gets the total number of frozen objects in the collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a14c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a14c-104">Syntax</span></span>  
  
```  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a14c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9a14c-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="9a14c-106">[out] Ein Zeiger auf die Anzahl der fixierten Objekte in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="9a14c-106">[out] A pointer to the number of frozen objects in the collection.</span></span>  
  
 <span data-ttu-id="9a14c-107">Diese Methode gibt stets 0 (null) in .NET Framework, Version 3.5 Service Pack 1 (SP1) und höheren Versionen.</span><span class="sxs-lookup"><span data-stu-id="9a14c-107">This method will always return zero in the .NET Framework version 3.5 Service Pack 1 (SP1) and later versions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a14c-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9a14c-108">Requirements</span></span>  
 <span data-ttu-id="9a14c-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a14c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a14c-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9a14c-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9a14c-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a14c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a14c-112">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a14c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a14c-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a14c-113">See Also</span></span>  
 [<span data-ttu-id="9a14c-114">ICorProfilerObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9a14c-114">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
