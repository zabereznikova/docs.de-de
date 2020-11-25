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
ms.openlocfilehash: 5a27f155021661022b27022bbb252e00dfa67255
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698779"
---
# <a name="icordebugsteppersetrangeil-method"></a><span data-ttu-id="4ac70-102">ICorDebugStepper::SetRangeIL-Methode</span><span class="sxs-lookup"><span data-stu-id="4ac70-102">ICorDebugStepper::SetRangeIL Method</span></span>

<span data-ttu-id="4ac70-103">Legt einen Wert fest, der angibt, ob Aufrufe von [ICorDebugStepper:: StepRange](icordebugstepper-steprange-method.md) Argument Werte übergeben, die relativ zum systemeigenen Code oder relativ zum MSIL-Code (Microsoft Intermediate Language) der Methode sind, die durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="4ac70-103">Sets a value that specifies whether calls to [ICorDebugStepper::StepRange](icordebugstepper-steprange-method.md) pass argument values that are relative to the native code or relative to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ac70-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4ac70-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRangeIL (  
    [in] BOOL    bIL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ac70-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4ac70-105">Parameters</span></span>  

 `bIL`  
 <span data-ttu-id="4ac70-106">in Legen Sie auf fest, `true` um anzugeben, dass die Bereiche mit dem MSIL-Code relativ sind.</span><span class="sxs-lookup"><span data-stu-id="4ac70-106">[in] Set to `true` to specify that the ranges are relative to the MSIL code.</span></span> <span data-ttu-id="4ac70-107">Legen Sie auf fest, `false` um anzugeben, dass die Bereiche relativ zum systemeigenen Code sind.</span><span class="sxs-lookup"><span data-stu-id="4ac70-107">Set to `false` to specify that the ranges are relative to the native code.</span></span> <span data-ttu-id="4ac70-108">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="4ac70-108">The default value is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ac70-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4ac70-109">Requirements</span></span>  

 <span data-ttu-id="4ac70-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ac70-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ac70-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4ac70-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ac70-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ac70-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ac70-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ac70-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
