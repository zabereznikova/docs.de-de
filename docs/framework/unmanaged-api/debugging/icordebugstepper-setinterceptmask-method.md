---
title: ICorDebugStepper::SetInterceptMask-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37b644227a6085352bed682f0ddd7c3455b54895
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760706"
---
# <a name="icordebugsteppersetinterceptmask-method"></a><span data-ttu-id="891ec-102">ICorDebugStepper::SetInterceptMask-Methode</span><span class="sxs-lookup"><span data-stu-id="891ec-102">ICorDebugStepper::SetInterceptMask Method</span></span>
<span data-ttu-id="891ec-103">Legt einen Wert, der angibt, die Typen von Code, der durchlaufen werden.</span><span class="sxs-lookup"><span data-stu-id="891ec-103">Sets a value that specifies the types of code that are stepped into.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="891ec-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="891ec-104">Syntax</span></span>  
  
```cpp  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="891ec-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="891ec-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="891ec-106">[in] Eine Kombination von Werten CorDebugIntercept-Enumeration, die die Codetypen angibt.</span><span class="sxs-lookup"><span data-stu-id="891ec-106">[in] A combination of values of the CorDebugIntercept enumeration that specifies the types of code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="891ec-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="891ec-107">Remarks</span></span>  
 <span data-ttu-id="891ec-108">Wenn das Bit für einen Interceptor festgelegt ist, wird die zugeordnetem abgeschlossen, wenn der angegebene Typ des Abfangen von Code erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="891ec-108">If the bit for an interceptor is set, the stepper will complete when the given type of intercepting code is encountered.</span></span> <span data-ttu-id="891ec-109">Wenn das Bit deaktiviert ist, wird die abgefangene Code übersprungen.</span><span class="sxs-lookup"><span data-stu-id="891ec-109">If the bit is cleared, the intercepting code will be skipped.</span></span>  
  
 <span data-ttu-id="891ec-110">Die `SetInterceptMask` Methode möglicherweise unvorhergesehene Interaktionen mit [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (aus Sicht des Benutzers).</span><span class="sxs-lookup"><span data-stu-id="891ec-110">The `SetInterceptMask` method may have unforeseen interactions with [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (from the user's point of view).</span></span> <span data-ttu-id="891ec-111">Z. B. wenn nur sichtbare (d. h. nicht-interne) Teil des Initialisierungscodes für die Klasse verfügt nicht über die Zuordnungsinformationen und STOP_NO_MAPPING_INFO ist nicht festgelegt (finden Sie unter der [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) Methode und die CorDebugUnmappedStop-Enumeration), wird die klasseninitialisierung die zugeordnetem überspringen.</span><span class="sxs-lookup"><span data-stu-id="891ec-111">For example, if the only visible (that is, non-internal) portion of class initialization code lacks mapping information and STOP_NO_MAPPING_INFO isn't set (see the [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) method and the CorDebugUnmappedStop enumeration), the stepper will step over the class initialization.</span></span> <span data-ttu-id="891ec-112">Standardmäßig wird nur der INTERCEPT_NONE-Wert, der die `CorDebugIntercept` -Enumeration verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="891ec-112">By default, only the INTERCEPT_NONE value of the `CorDebugIntercept` enumeration will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="891ec-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="891ec-113">Requirements</span></span>  
 <span data-ttu-id="891ec-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="891ec-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="891ec-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="891ec-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="891ec-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="891ec-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="891ec-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="891ec-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
