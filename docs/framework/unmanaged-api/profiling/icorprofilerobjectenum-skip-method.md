---
title: ICorProfilerObjectEnum::Skip-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerObjectEnum.Skip
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerObjectEnum::Skip
helpviewer_keywords:
- ICorProfilerObjectEnum::Skip method [.NET Framework profiling]
- Skip method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: f8e498f8-f93a-4b82-bd22-55bdbf5e8d45
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 84960af6e128f3a6aa9e3b45187e282ac7228e0f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerobjectenumskip-method"></a><span data-ttu-id="e5135-102">ICorProfilerObjectEnum::Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="e5135-102">ICorProfilerObjectEnum::Skip Method</span></span>
<span data-ttu-id="e5135-103">Setzt den Cursor über dieser Enumerator aus seiner aktuellen Position an, damit, dass die angegebene Anzahl von Elementen übersprungen wird.</span><span class="sxs-lookup"><span data-stu-id="e5135-103">Advances the cursor of this enumerator from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5135-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e5135-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e5135-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e5135-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="e5135-106">[in] Die Anzahl von Elementen übersprungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="e5135-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5135-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e5135-107">Remarks</span></span>  
 <span data-ttu-id="e5135-108">Die neue Position der Cursor des Enumerators ist: (aktuelle Position) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="e5135-108">The new position of this enumerator's cursor is: (current position) + `celt` .</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5135-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e5135-109">Requirements</span></span>  
 <span data-ttu-id="e5135-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5135-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5135-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e5135-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e5135-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5135-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5135-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5135-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5135-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5135-114">See Also</span></span>  
 [<span data-ttu-id="e5135-115">ICorProfilerObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e5135-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
