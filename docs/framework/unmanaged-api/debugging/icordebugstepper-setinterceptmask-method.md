---
title: ICorDebugStepper::SetInterceptMask-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugStepper.SetInterceptMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetInterceptMask
helpviewer_keywords:
- SetInterceptMask method [.NET Framework debugging]
- ICorDebugStepper::SetInterceptMask method [.NET Framework debugging]
ms.assetid: 6245e2ae-5cc2-43ff-8cc1-71953d12113a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3ef03b63c4af79c01ba9962fcc6f106b3141b576
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsteppersetinterceptmask-method"></a><span data-ttu-id="aa97b-102">ICorDebugStepper::SetInterceptMask-Methode</span><span class="sxs-lookup"><span data-stu-id="aa97b-102">ICorDebugStepper::SetInterceptMask Method</span></span>
<span data-ttu-id="aa97b-103">Legt einen Wert, der angibt, die Typen von Code, der durchlaufen werden.</span><span class="sxs-lookup"><span data-stu-id="aa97b-103">Sets a value that specifies the types of code that are stepped into.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa97b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa97b-104">Syntax</span></span>  
  
```  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aa97b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="aa97b-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="aa97b-106">[in] Eine Kombination von Werten CorDebugIntercept-Enumeration, die die Codetypen angibt.</span><span class="sxs-lookup"><span data-stu-id="aa97b-106">[in] A combination of values of the CorDebugIntercept enumeration that specifies the types of code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa97b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aa97b-107">Remarks</span></span>  
 <span data-ttu-id="aa97b-108">Wenn das Bit für einen Interceptor festgelegt ist, wird der zugeordnetem vervollständigt, wenn es sich bei der jeweiligen Typ der abfangen Code aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="aa97b-108">If the bit for an interceptor is set, the stepper will complete when the given type of intercepting code is encountered.</span></span> <span data-ttu-id="aa97b-109">Wenn das Bit deaktiviert ist, wird die abgefangene Code übersprungen.</span><span class="sxs-lookup"><span data-stu-id="aa97b-109">If the bit is cleared, the intercepting code will be skipped.</span></span>  
  
 <span data-ttu-id="aa97b-110">Die `SetInterceptMask` Methode möglicherweise unvorhergesehene Interaktionen mit [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (aus Sicht des Benutzers).</span><span class="sxs-lookup"><span data-stu-id="aa97b-110">The `SetInterceptMask` method may have unforeseen interactions with [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (from the user's point of view).</span></span> <span data-ttu-id="aa97b-111">Z. B. wenn nur sichtbar (d. h.-interner) Teil des Initialisierungscodes für die Klasse verfügt nicht über die Zuordnungsinformationen und STOP_NO_MAPPING_INFO nicht festgelegt ist (finden Sie unter der [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) Methode und die CorDebugUnmappedStop-Enumeration), wird die Initialisierung der Klasse die zugeordnetem überspringen.</span><span class="sxs-lookup"><span data-stu-id="aa97b-111">For example, if the only visible (that is, non-internal) portion of class initialization code lacks mapping information and STOP_NO_MAPPING_INFO isn't set (see the [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) method and the CorDebugUnmappedStop enumeration), the stepper will step over the class initialization.</span></span> <span data-ttu-id="aa97b-112">Standardmäßig wird nur der INTERCEPT_NONE-Wert, der die `CorDebugIntercept` Enumeration verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aa97b-112">By default, only the INTERCEPT_NONE value of the `CorDebugIntercept` enumeration will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa97b-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="aa97b-113">Requirements</span></span>  
 <span data-ttu-id="aa97b-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa97b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa97b-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aa97b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aa97b-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa97b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa97b-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa97b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
