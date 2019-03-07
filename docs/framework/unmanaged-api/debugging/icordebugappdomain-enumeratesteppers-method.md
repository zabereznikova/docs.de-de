---
title: ICorDebugAppDomain::EnumerateSteppers-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateSteppers
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateSteppers
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateSteppers method [.NET Framework debugging]
- EnumerateSteppers method [.NET Framework debugging]
ms.assetid: 3f3c4503-570e-44c1-ae6a-a3c6b840c732
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d326c801ed17fa6fe79f9e464e64844d0016e572
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489351"
---
# <a name="icordebugappdomainenumeratesteppers-method"></a><span data-ttu-id="ea505-102">ICorDebugAppDomain::EnumerateSteppers-Methode</span><span class="sxs-lookup"><span data-stu-id="ea505-102">ICorDebugAppDomain::EnumerateSteppers Method</span></span>
<span data-ttu-id="ea505-103">Ruft einen Enumerator für alle aktiven Stepper in der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="ea505-103">Gets an enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea505-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ea505-104">Syntax</span></span>  
  
```  
HRESULT EnumerateSteppers (  
    [out] ICorDebugStepperEnum   **ppSteppers  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea505-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ea505-105">Parameters</span></span>  
 `ppSteppers`  
 <span data-ttu-id="ea505-106">[out] Ein Zeiger auf die Adresse des ICorDebugStepperEnum-Objekts, das den Enumerator für alle aktiven Stepper in der Anwendungsdomäne ist.</span><span class="sxs-lookup"><span data-stu-id="ea505-106">[out] A pointer to the address of an ICorDebugStepperEnum object that is the enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea505-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ea505-107">Requirements</span></span>  
 <span data-ttu-id="ea505-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea505-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea505-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ea505-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ea505-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea505-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea505-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea505-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
