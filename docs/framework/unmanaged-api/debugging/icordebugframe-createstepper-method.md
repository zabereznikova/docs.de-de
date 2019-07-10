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
ms.openlocfilehash: fd105a5cbdb857aaa902e60968ff1d94473259b6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754239"
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="2fbb5-102">ICorDebugFrame::CreateStepper-Methode</span><span class="sxs-lookup"><span data-stu-id="2fbb5-102">ICorDebugFrame::CreateStepper Method</span></span>
<span data-ttu-id="2fbb5-103">Ruft ab eine zugeordnetem, die mit dem Debugger zum schrittweisen Operationen in Bezug auf diesem ICorDebugFrame ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="2fbb5-103">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fbb5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2fbb5-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fbb5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2fbb5-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="2fbb5-106">[out] Ein Zeiger auf die Adresse des ein ICorDebugStepper-Objekt, das mit dem Debugger zum schrittweisen Operationen in Bezug auf den aktuellen Frame ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="2fbb5-106">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2fbb5-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2fbb5-107">Remarks</span></span>  
 <span data-ttu-id="2fbb5-108">Wenn der Frame nicht aktiv ist, müssen das zugeordnetem-Objekt in der Regel auf den Frame zurück, bevor der Schritt abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="2fbb5-108">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fbb5-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2fbb5-109">Requirements</span></span>  
 <span data-ttu-id="2fbb5-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fbb5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fbb5-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2fbb5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2fbb5-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2fbb5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2fbb5-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fbb5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
