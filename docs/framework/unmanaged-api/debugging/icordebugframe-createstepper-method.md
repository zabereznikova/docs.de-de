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
ms.openlocfilehash: 6ea2b24d37f56a5cb9e6b3dea0d666c8acc719dc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73091031"
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="9abd6-102">ICorDebugFrame::CreateStepper-Methode</span><span class="sxs-lookup"><span data-stu-id="9abd6-102">ICorDebugFrame::CreateStepper Method</span></span>
<span data-ttu-id="9abd6-103">Ruft einen Stepper ab, der dem Debugger das Ausführen von schrittweise Vorgängen in Relation zu diesem ICorDebugFrame ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="9abd6-103">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9abd6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9abd6-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9abd6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9abd6-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="9abd6-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugStepper-Objekts, das es dem Debugger ermöglicht, schrittweise Vorgänge in Relation zum aktuellen Frame auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9abd6-106">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9abd6-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9abd6-107">Remarks</span></span>  
 <span data-ttu-id="9abd6-108">Wenn der Frame nicht aktiv ist, muss das Stepper-Objekt in der Regel zum Frame zurückkehren, bevor der Schritt abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="9abd6-108">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9abd6-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9abd6-109">Requirements</span></span>  
 <span data-ttu-id="9abd6-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9abd6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9abd6-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9abd6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9abd6-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9abd6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9abd6-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9abd6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
