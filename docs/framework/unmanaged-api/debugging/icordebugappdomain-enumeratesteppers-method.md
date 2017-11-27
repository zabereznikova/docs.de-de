---
title: ICorDebugAppDomain::EnumerateSteppers-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain.EnumerateSteppers
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain::EnumerateSteppers
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateSteppers method [.NET Framework debugging]
- EnumerateSteppers method [.NET Framework debugging]
ms.assetid: 3f3c4503-570e-44c1-ae6a-a3c6b840c732
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5e58059bbd3e9bf8d3db80d36e84e1f4496eb0bf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomainenumeratesteppers-method"></a><span data-ttu-id="fadfb-102">ICorDebugAppDomain::EnumerateSteppers-Methode</span><span class="sxs-lookup"><span data-stu-id="fadfb-102">ICorDebugAppDomain::EnumerateSteppers Method</span></span>
<span data-ttu-id="fadfb-103">Ruft einen Enumerator für alle aktiven Stepper in der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="fadfb-103">Gets an enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fadfb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fadfb-104">Syntax</span></span>  
  
```  
HRESULT EnumerateSteppers (  
    [out] ICorDebugStepperEnum   **ppSteppers  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fadfb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fadfb-105">Parameters</span></span>  
 `ppSteppers`  
 <span data-ttu-id="fadfb-106">[out] Ein Zeiger auf die Adresse eines ICorDebugStepperEnum-Objekts, das den Enumerator für alle aktiven Stepper in der Anwendungsdomäne ist.</span><span class="sxs-lookup"><span data-stu-id="fadfb-106">[out] A pointer to the address of an ICorDebugStepperEnum object that is the enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fadfb-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fadfb-107">Requirements</span></span>  
 <span data-ttu-id="fadfb-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fadfb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fadfb-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fadfb-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fadfb-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fadfb-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fadfb-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fadfb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
