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
ms.openlocfilehash: 50fad8b38a6b33d0ddbb2f0f20676296c3d66737
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698740"
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a><span data-ttu-id="ef756-102">ICorDebugStepper::SetUnmappedStopMask-Methode</span><span class="sxs-lookup"><span data-stu-id="ef756-102">ICorDebugStepper::SetUnmappedStopMask Method</span></span>

<span data-ttu-id="ef756-103">Legt einen Wert fest, der den Typ des nicht zugeordneten Codes angibt, in dem die Ausführung angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="ef756-103">Sets a value that specifies the type of unmapped code in which execution will halt.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef756-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ef756-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef756-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ef756-105">Parameters</span></span>  

 `mask`  
 <span data-ttu-id="ef756-106">in Ein Wert der CorDebugUnmappedStop-Enumeration, der den Typ des nicht zugeordneten Codes angibt, in dem der Debugger die Ausführung stoppt.</span><span class="sxs-lookup"><span data-stu-id="ef756-106">[in] A value of the CorDebugUnmappedStop enumeration that specifies the type of unmapped code in which the debugger will halt execution.</span></span>  
  
 <span data-ttu-id="ef756-107">Der Standardwert ist STOP_OTHER_UNMAPPED.</span><span class="sxs-lookup"><span data-stu-id="ef756-107">The default value is STOP_OTHER_UNMAPPED.</span></span> <span data-ttu-id="ef756-108">Der Wert STOP_UNMANAGED der nur beim Interop-Debuggen gültig ist.</span><span class="sxs-lookup"><span data-stu-id="ef756-108">The value STOP_UNMANAGED is only valid with interop debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef756-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ef756-109">Remarks</span></span>  

 <span data-ttu-id="ef756-110">Wenn der Debugger eine Just-in-time (JIT)-Kompilierung findet, die keine entsprechende Zuordnung zur Microsoft Intermediate Language (MSIL) aufweist, wird die Ausführung angehalten, wenn das Flag, das den Typ des nicht zugeordneten Codes angibt, festgelegt wurde. Andernfalls wird die schrittweise transparente fortgeführt.</span><span class="sxs-lookup"><span data-stu-id="ef756-110">When the debugger finds a just-in-time (JIT) compilation that has no corresponding mapping to Microsoft intermediate language (MSIL), it halts execution if the flag specifying that type of unmapped code has been set; otherwise, stepping transparently continues.</span></span>  
  
 <span data-ttu-id="ef756-111">Wenn der Debugger keinen Stepper verwendet, um eine Methode einzugeben, wird der nicht zugeordnete Code nicht notwendigerweise überschrit.</span><span class="sxs-lookup"><span data-stu-id="ef756-111">If the debugger doesn't use a stepper to enter a method, then it won't necessarily step over unmapped code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef756-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ef756-112">Requirements</span></span>  

 <span data-ttu-id="ef756-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef756-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef756-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ef756-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef756-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef756-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef756-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef756-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
