---
title: ICorDebugFrame::CreateStepper-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFrame.CreateStepper
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFrame::CreateStepper
helpviewer_keywords:
- ICorDebugFrame::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 689e7f28-20c1-4d5c-9baa-17441cd63a88
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 93f6741a030e72406fb8099c6373896d14cb9332
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="5f498-102">ICorDebugFrame::CreateStepper-Methode</span><span class="sxs-lookup"><span data-stu-id="5f498-102">ICorDebugFrame::CreateStepper Method</span></span>
<span data-ttu-id="5f498-103">Ruft eine zugeordnetem, die dem Debugger ermöglicht, die relativ zu diesem ICorDebugFrame schrittweisen Vorgänge ab.</span><span class="sxs-lookup"><span data-stu-id="5f498-103">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f498-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5f498-104">Syntax</span></span>  
  
```  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5f498-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5f498-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="5f498-106">[out] Ein Zeiger auf die Adresse eines ICorDebugStepper-Objekts, das dem Debugger ermöglicht, relativ zum aktuellen Rahmen schrittweisen Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="5f498-106">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f498-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5f498-107">Remarks</span></span>  
 <span data-ttu-id="5f498-108">Wenn der Frame nicht aktiv ist, müssen das zugeordnetem-Objekt in der Regel auf den Frame zurück, bevor der Schritt abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="5f498-108">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f498-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5f498-109">Requirements</span></span>  
 <span data-ttu-id="5f498-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f498-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f498-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f498-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f498-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f498-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f498-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f498-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
