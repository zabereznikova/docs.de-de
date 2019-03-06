---
title: ICorDebugStepper::SetUnmappedStopMask-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetUnmappedStopMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetUnmappedStopMask
helpviewer_keywords:
- ICorDebugStepper::SetUnmappedStopMask method [.NET Framework debugging]
- SetUnmappedStopMask method [.NET Framework debugging]
ms.assetid: b1211981-e90c-4e05-8def-fa18d85ad9ab
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da799b0d4f4e5e4b281445baa35d95f992ba0b63
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474955"
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a><span data-ttu-id="4e789-102">ICorDebugStepper::SetUnmappedStopMask-Methode</span><span class="sxs-lookup"><span data-stu-id="4e789-102">ICorDebugStepper::SetUnmappedStopMask Method</span></span>
<span data-ttu-id="4e789-103">Legt einen Wert, der den Typ von nicht zugeordnetem Code gibt an, in dem die Ausführung angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="4e789-103">Sets a value that specifies the type of unmapped code in which execution will halt.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e789-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e789-104">Syntax</span></span>  
  
```  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e789-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4e789-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="4e789-106">[in] Der Wert der CorDebugUnmappedStop-Enumeration, die den Typ des nicht zugeordneten Codes angibt, in dem der Debugger die Ausführung angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="4e789-106">[in] A value of the CorDebugUnmappedStop enumeration that specifies the type of unmapped code in which the debugger will halt execution.</span></span>  
  
 <span data-ttu-id="4e789-107">Der Standardwert ist STOP_OTHER_UNMAPPED.</span><span class="sxs-lookup"><span data-stu-id="4e789-107">The default value is STOP_OTHER_UNMAPPED.</span></span> <span data-ttu-id="4e789-108">Der Wert STOP_UNMANAGED ist nur gültig mit der interop-Debuggen.</span><span class="sxs-lookup"><span data-stu-id="4e789-108">The value STOP_UNMANAGED is only valid with interop debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e789-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4e789-109">Remarks</span></span>  
 <span data-ttu-id="4e789-110">Wenn der Debugger eine just-in-Time-Kompilierung (JIT), die keine entsprechende Zuordnung Microsoft intermediate Language (MSIL) aufweist findet, hält er Ausführung, wenn das Flag, das diesen Typ von nicht zugeordnetem Code angeben festgelegt wurde; Andernfalls wird die transparente schrittweise Ausführung fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="4e789-110">When the debugger finds a just-in-time (JIT) compilation that has no corresponding mapping to Microsoft intermediate language (MSIL), it halts execution if the flag specifying that type of unmapped code has been set; otherwise, stepping transparently continues.</span></span>  
  
 <span data-ttu-id="4e789-111">Wenn der Debugger eine zugeordnetem nicht verwendet, eine Methode einzugeben, wird nicht es unbedingt nicht zugeordnetem Code überspringen.</span><span class="sxs-lookup"><span data-stu-id="4e789-111">If the debugger doesn't use a stepper to enter a method, then it won't necessarily step over unmapped code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e789-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4e789-112">Requirements</span></span>  
 <span data-ttu-id="4e789-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e789-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e789-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4e789-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4e789-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e789-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e789-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e789-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
