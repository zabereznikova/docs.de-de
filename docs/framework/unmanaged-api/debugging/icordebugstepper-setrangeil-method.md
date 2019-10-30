---
title: ICorDebugStepper::SetRangeIL-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetRangeIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetRangeIL
helpviewer_keywords:
- SetRangeIL method [.NET Framework debugging]
- ICorDebugStepper::SetRangeIL method [.NET Framework debugging]
ms.assetid: a20c95f0-6da7-4b41-b27f-584211cebb92
topic_type:
- apiref
ms.openlocfilehash: 88270cb73515cc1a671bfb3fb5c479697ad7b359
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137541"
---
# <a name="icordebugsteppersetrangeil-method"></a><span data-ttu-id="27424-102">ICorDebugStepper::SetRangeIL-Methode</span><span class="sxs-lookup"><span data-stu-id="27424-102">ICorDebugStepper::SetRangeIL Method</span></span>
<span data-ttu-id="27424-103">Legt einen Wert fest, der angibt, ob Aufrufe von [ICorDebugStepper:: StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) Argument Werte übergeben, die relativ zum systemeigenen Code oder relativ zum MSIL-Code (Microsoft Intermediate Language) der Methode sind, die durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="27424-103">Sets a value that specifies whether calls to [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pass argument values that are relative to the native code or relative to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27424-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="27424-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRangeIL (  
    [in] BOOL    bIL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27424-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="27424-105">Parameters</span></span>  
 `bIL`  
 <span data-ttu-id="27424-106">in Legen Sie diese Einstellung auf `true` fest, um anzugeben, dass die Bereiche mit dem MSIL-Code relativ sind.</span><span class="sxs-lookup"><span data-stu-id="27424-106">[in] Set to `true` to specify that the ranges are relative to the MSIL code.</span></span> <span data-ttu-id="27424-107">Legen Sie diese Einstellung auf `false` fest, um anzugeben, dass die Bereiche relativ zum systemeigenen Code sind.</span><span class="sxs-lookup"><span data-stu-id="27424-107">Set to `false` to specify that the ranges are relative to the native code.</span></span> <span data-ttu-id="27424-108">Der Standardwert ist `true`sein.</span><span class="sxs-lookup"><span data-stu-id="27424-108">The default value is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27424-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="27424-109">Requirements</span></span>  
 <span data-ttu-id="27424-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27424-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27424-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27424-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27424-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27424-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27424-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27424-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
