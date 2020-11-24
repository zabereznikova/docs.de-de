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
ms.openlocfilehash: 5dfb64d0c440cbd2c8a8a65b2c18d78f02a7615e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679714"
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="295cc-102">ICorDebugFrame::CreateStepper-Methode</span><span class="sxs-lookup"><span data-stu-id="295cc-102">ICorDebugFrame::CreateStepper Method</span></span>

<span data-ttu-id="295cc-103">Ruft einen Stepper ab, der dem Debugger das Ausführen von schrittweise Vorgängen in Relation zu diesem ICorDebugFrame ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="295cc-103">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="295cc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="295cc-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="295cc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="295cc-105">Parameters</span></span>  

 `ppStepper`  
 <span data-ttu-id="295cc-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugStepper-Objekts, das es dem Debugger ermöglicht, schrittweise Vorgänge in Relation zum aktuellen Frame auszuführen.</span><span class="sxs-lookup"><span data-stu-id="295cc-106">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="295cc-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="295cc-107">Remarks</span></span>  

 <span data-ttu-id="295cc-108">Wenn der Frame nicht aktiv ist, muss das Stepper-Objekt in der Regel zum Frame zurückkehren, bevor der Schritt abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="295cc-108">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="295cc-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="295cc-109">Requirements</span></span>  

 <span data-ttu-id="295cc-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="295cc-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="295cc-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="295cc-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="295cc-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="295cc-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="295cc-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="295cc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
