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
ms.openlocfilehash: 814bf87039ef57056f13994af1b873f8f57c7804
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718214"
---
# <a name="icordebugsteppersetinterceptmask-method"></a><span data-ttu-id="d7b37-102">ICorDebugStepper::SetInterceptMask-Methode</span><span class="sxs-lookup"><span data-stu-id="d7b37-102">ICorDebugStepper::SetInterceptMask Method</span></span>

<span data-ttu-id="d7b37-103">Legt einen Wert fest, der die Typen von Code angibt, die in Einzelschritten werden.</span><span class="sxs-lookup"><span data-stu-id="d7b37-103">Sets a value that specifies the types of code that are stepped into.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7b37-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d7b37-104">Syntax</span></span>  
  
```cpp  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7b37-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d7b37-105">Parameters</span></span>  

 `mask`  
 <span data-ttu-id="d7b37-106">in Eine Kombination von Werten der CorDebugIntercept-Enumeration, die die Codetypen angibt.</span><span class="sxs-lookup"><span data-stu-id="d7b37-106">[in] A combination of values of the CorDebugIntercept enumeration that specifies the types of code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7b37-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d7b37-107">Remarks</span></span>  

 <span data-ttu-id="d7b37-108">Wenn das Bit für einen Interceptor festgelegt ist, wird der Stepper vervollständigt, wenn der angegebene Typ des Abfang Codes auftritt.</span><span class="sxs-lookup"><span data-stu-id="d7b37-108">If the bit for an interceptor is set, the stepper will complete when the given type of intercepting code is encountered.</span></span> <span data-ttu-id="d7b37-109">Wenn das Bit deaktiviert ist, wird der abfängt Code übersprungen.</span><span class="sxs-lookup"><span data-stu-id="d7b37-109">If the bit is cleared, the intercepting code will be skipped.</span></span>  
  
 <span data-ttu-id="d7b37-110">Die- `SetInterceptMask` Methode hat möglicherweise unvorhergesehene Interaktionen mit [ICorDebugStepper:: seetunmappedstopmask](icordebugstepper-setunmappedstopmask-method.md) (aus Sicht des Benutzers).</span><span class="sxs-lookup"><span data-stu-id="d7b37-110">The `SetInterceptMask` method may have unforeseen interactions with [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) (from the user's point of view).</span></span> <span data-ttu-id="d7b37-111">Wenn z. b. der einzige sichtbare (d. h. nicht interne) Teil des Initialisierungs Codes der Klasse keine Mappinginformationen hat und STOP_NO_MAPPING_INFO nicht festgelegt ist (siehe die [ICorDebugStepper:: SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) -Methode und die CorDebugUnmappedStop-Enumeration), wird der Stepper die Initialisierung der Klasse überschreiten.</span><span class="sxs-lookup"><span data-stu-id="d7b37-111">For example, if the only visible (that is, non-internal) portion of class initialization code lacks mapping information and STOP_NO_MAPPING_INFO isn't set (see the [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) method and the CorDebugUnmappedStop enumeration), the stepper will step over the class initialization.</span></span> <span data-ttu-id="d7b37-112">Standardmäßig wird nur der INTERCEPT_NONE Wert der- `CorDebugIntercept` Enumeration verwendet.</span><span class="sxs-lookup"><span data-stu-id="d7b37-112">By default, only the INTERCEPT_NONE value of the `CorDebugIntercept` enumeration will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7b37-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d7b37-113">Requirements</span></span>  

 <span data-ttu-id="d7b37-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7b37-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7b37-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7b37-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7b37-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7b37-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7b37-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7b37-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
