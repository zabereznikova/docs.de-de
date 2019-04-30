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
ms.openlocfilehash: 3fe3cbc4bad83496bcc58aaea60e6724b1d1f06c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988896"
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="4bfe8-102">ICorDebugFrame::CreateStepper-Methode</span><span class="sxs-lookup"><span data-stu-id="4bfe8-102">ICorDebugFrame::CreateStepper Method</span></span>
<span data-ttu-id="4bfe8-103">Ruft ab eine zugeordnetem, die mit dem Debugger zum schrittweisen Operationen in Bezug auf diesem ICorDebugFrame ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="4bfe8-103">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bfe8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4bfe8-104">Syntax</span></span>  
  
```  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4bfe8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4bfe8-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="4bfe8-106">[out] Ein Zeiger auf die Adresse des ein ICorDebugStepper-Objekt, das mit dem Debugger zum schrittweisen Operationen in Bezug auf den aktuellen Frame ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="4bfe8-106">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4bfe8-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4bfe8-107">Remarks</span></span>  
 <span data-ttu-id="4bfe8-108">Wenn der Frame nicht aktiv ist, müssen das zugeordnetem-Objekt in der Regel auf den Frame zurück, bevor der Schritt abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="4bfe8-108">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bfe8-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4bfe8-109">Requirements</span></span>  
 <span data-ttu-id="4bfe8-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bfe8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bfe8-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4bfe8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4bfe8-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4bfe8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4bfe8-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bfe8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
