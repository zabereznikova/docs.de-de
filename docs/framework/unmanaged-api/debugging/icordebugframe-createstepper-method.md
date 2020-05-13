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
ms.openlocfilehash: 39b4e7e5123447a36254b55b6168c80e48c8dcab
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205449"
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="8447d-102">ICorDebugFrame::CreateStepper-Methode</span><span class="sxs-lookup"><span data-stu-id="8447d-102">ICorDebugFrame::CreateStepper Method</span></span>
<span data-ttu-id="8447d-103">Ruft einen Stepper ab, der dem Debugger das Ausführen von schrittweise Vorgängen in Relation zu diesem ICorDebugFrame ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="8447d-103">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8447d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8447d-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8447d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8447d-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="8447d-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugStepper-Objekts, das es dem Debugger ermöglicht, schrittweise Vorgänge in Relation zum aktuellen Frame auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8447d-106">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8447d-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8447d-107">Remarks</span></span>  
 <span data-ttu-id="8447d-108">Wenn der Frame nicht aktiv ist, muss das Stepper-Objekt in der Regel zum Frame zurückkehren, bevor der Schritt abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="8447d-108">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8447d-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8447d-109">Requirements</span></span>  
 <span data-ttu-id="8447d-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8447d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8447d-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8447d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8447d-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8447d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8447d-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8447d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
