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
ms.openlocfilehash: a6f575febc488d01700c32198d4c00916dd5e249
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="0f199-102">ICorDebugFrame::CreateStepper-Methode</span><span class="sxs-lookup"><span data-stu-id="0f199-102">ICorDebugFrame::CreateStepper Method</span></span>
<span data-ttu-id="0f199-103">Ruft eine zugeordnetem, die dem Debugger ermöglicht, die relativ zu diesem ICorDebugFrame schrittweisen Vorgänge ab.</span><span class="sxs-lookup"><span data-stu-id="0f199-103">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f199-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f199-104">Syntax</span></span>  
  
```  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f199-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0f199-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="0f199-106">[out] Ein Zeiger auf die Adresse eines ICorDebugStepper-Objekts, das dem Debugger ermöglicht, relativ zum aktuellen Rahmen schrittweisen Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="0f199-106">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f199-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0f199-107">Remarks</span></span>  
 <span data-ttu-id="0f199-108">Wenn der Frame nicht aktiv ist, müssen das zugeordnetem-Objekt in der Regel auf den Frame zurück, bevor der Schritt abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="0f199-108">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f199-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0f199-109">Requirements</span></span>  
 <span data-ttu-id="0f199-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f199-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f199-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f199-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f199-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f199-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f199-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f199-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
