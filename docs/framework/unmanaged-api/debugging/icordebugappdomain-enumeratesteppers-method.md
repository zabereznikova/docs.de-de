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
ms.openlocfilehash: a736990188023031eb8df5a76dd16fcc289cfe20
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134034"
---
# <a name="icordebugappdomainenumeratesteppers-method"></a><span data-ttu-id="fe2f1-102">ICorDebugAppDomain::EnumerateSteppers-Methode</span><span class="sxs-lookup"><span data-stu-id="fe2f1-102">ICorDebugAppDomain::EnumerateSteppers Method</span></span>
<span data-ttu-id="fe2f1-103">Ruft einen Enumerator für alle aktiven Steppers in der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="fe2f1-103">Gets an enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe2f1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fe2f1-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateSteppers (  
    [out] ICorDebugStepperEnum   **ppSteppers  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe2f1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fe2f1-105">Parameters</span></span>  
 `ppSteppers`  
 <span data-ttu-id="fe2f1-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugStepperEnum-Objekts, das der Enumerator für alle aktiven Steppers in der Anwendungsdomäne ist.</span><span class="sxs-lookup"><span data-stu-id="fe2f1-106">[out] A pointer to the address of an ICorDebugStepperEnum object that is the enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe2f1-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fe2f1-107">Requirements</span></span>  
 <span data-ttu-id="fe2f1-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe2f1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe2f1-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe2f1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe2f1-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe2f1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe2f1-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe2f1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
