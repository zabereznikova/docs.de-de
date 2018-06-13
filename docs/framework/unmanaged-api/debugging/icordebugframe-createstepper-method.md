---
title: ICorDebugFrame::CreateStepper-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::CreateStepper
helpviewer_keywords:
- ICorDebugFrame::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 689e7f28-20c1-4d5c-9baa-17441cd63a88
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3662ed8a3fda5881b0e0929a830d19b0d805299f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411030"
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="63d13-102">ICorDebugFrame::CreateStepper-Methode</span><span class="sxs-lookup"><span data-stu-id="63d13-102">ICorDebugFrame::CreateStepper Method</span></span>
<span data-ttu-id="63d13-103">Ruft eine zugeordnetem, die dem Debugger ermöglicht, die relativ zu diesem ICorDebugFrame schrittweisen Vorgänge ab.</span><span class="sxs-lookup"><span data-stu-id="63d13-103">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63d13-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="63d13-104">Syntax</span></span>  
  
```  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="63d13-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="63d13-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="63d13-106">[out] Ein Zeiger auf die Adresse eines ICorDebugStepper-Objekts, das dem Debugger ermöglicht, relativ zum aktuellen Rahmen schrittweisen Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="63d13-106">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63d13-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="63d13-107">Remarks</span></span>  
 <span data-ttu-id="63d13-108">Wenn der Frame nicht aktiv ist, müssen das zugeordnetem-Objekt in der Regel auf den Frame zurück, bevor der Schritt abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="63d13-108">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63d13-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="63d13-109">Requirements</span></span>  
 <span data-ttu-id="63d13-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63d13-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63d13-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63d13-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63d13-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63d13-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63d13-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63d13-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
