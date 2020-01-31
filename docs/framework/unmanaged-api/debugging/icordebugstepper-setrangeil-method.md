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
ms.openlocfilehash: b3153a88867d249aad8365bb774348fb8c9d57d5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791749"
---
# <a name="icordebugsteppersetrangeil-method"></a><span data-ttu-id="9b700-102">ICorDebugStepper::SetRangeIL-Methode</span><span class="sxs-lookup"><span data-stu-id="9b700-102">ICorDebugStepper::SetRangeIL Method</span></span>
<span data-ttu-id="9b700-103">Legt einen Wert fest, der angibt, ob Aufrufe von [ICorDebugStepper:: StepRange](icordebugstepper-steprange-method.md) Argument Werte übergeben, die relativ zum systemeigenen Code oder relativ zum MSIL-Code (Microsoft Intermediate Language) der Methode sind, die durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="9b700-103">Sets a value that specifies whether calls to [ICorDebugStepper::StepRange](icordebugstepper-steprange-method.md) pass argument values that are relative to the native code or relative to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b700-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b700-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRangeIL (  
    [in] BOOL    bIL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b700-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="9b700-105">Parameters</span></span>  
 `bIL`  
 <span data-ttu-id="9b700-106">in Legen Sie diese Einstellung auf `true` fest, um anzugeben, dass die Bereiche mit dem MSIL-Code relativ sind.</span><span class="sxs-lookup"><span data-stu-id="9b700-106">[in] Set to `true` to specify that the ranges are relative to the MSIL code.</span></span> <span data-ttu-id="9b700-107">Legen Sie diese Einstellung auf `false` fest, um anzugeben, dass die Bereiche relativ zum systemeigenen Code sind.</span><span class="sxs-lookup"><span data-stu-id="9b700-107">Set to `false` to specify that the ranges are relative to the native code.</span></span> <span data-ttu-id="9b700-108">Der Standardwert ist `true`sein.</span><span class="sxs-lookup"><span data-stu-id="9b700-108">The default value is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b700-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9b700-109">Requirements</span></span>  
 <span data-ttu-id="9b700-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b700-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b700-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b700-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b700-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b700-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b700-113">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b700-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
