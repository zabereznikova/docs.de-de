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
ms.openlocfilehash: fd9243d9e0c12b572613694538661fd553e8a487
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715926"
---
# <a name="icordebugappdomainenumeratesteppers-method"></a><span data-ttu-id="3d570-102">ICorDebugAppDomain::EnumerateSteppers-Methode</span><span class="sxs-lookup"><span data-stu-id="3d570-102">ICorDebugAppDomain::EnumerateSteppers Method</span></span>

<span data-ttu-id="3d570-103">Ruft einen Enumerator für alle aktiven Steppers in der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="3d570-103">Gets an enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d570-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3d570-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateSteppers (  
    [out] ICorDebugStepperEnum   **ppSteppers  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d570-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3d570-105">Parameters</span></span>  

 `ppSteppers`  
 <span data-ttu-id="3d570-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugStepperEnum-Objekts, das der Enumerator für alle aktiven Steppers in der Anwendungsdomäne ist.</span><span class="sxs-lookup"><span data-stu-id="3d570-106">[out] A pointer to the address of an ICorDebugStepperEnum object that is the enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d570-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3d570-107">Requirements</span></span>  

 <span data-ttu-id="3d570-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d570-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d570-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d570-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d570-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d570-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d570-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d570-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
