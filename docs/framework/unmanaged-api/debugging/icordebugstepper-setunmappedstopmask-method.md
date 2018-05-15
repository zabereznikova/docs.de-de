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
ms.openlocfilehash: dc4e51ec60c7526f36bbe4909bec91a527e0862c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a><span data-ttu-id="3a095-102">ICorDebugStepper::SetUnmappedStopMask-Methode</span><span class="sxs-lookup"><span data-stu-id="3a095-102">ICorDebugStepper::SetUnmappedStopMask Method</span></span>
<span data-ttu-id="3a095-103">Legt einen Wert, der den Typ des nicht zugeordneten Codes angibt, in dem die Ausführung angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="3a095-103">Sets a value that specifies the type of unmapped code in which execution will halt.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a095-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a095-104">Syntax</span></span>  
  
```  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3a095-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3a095-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="3a095-106">[in] Der Wert der CorDebugUnmappedStop-Enumeration, die den Typ des nicht zugeordneten Codes angibt, in dem der Debugger die Ausführung angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="3a095-106">[in] A value of the CorDebugUnmappedStop enumeration that specifies the type of unmapped code in which the debugger will halt execution.</span></span>  
  
 <span data-ttu-id="3a095-107">Der Standardwert ist STOP_OTHER_UNMAPPED.</span><span class="sxs-lookup"><span data-stu-id="3a095-107">The default value is STOP_OTHER_UNMAPPED.</span></span> <span data-ttu-id="3a095-108">Der Wert STOP_UNMANAGED ist nur gültig, wenn Interop-Debuggen.</span><span class="sxs-lookup"><span data-stu-id="3a095-108">The value STOP_UNMANAGED is only valid with interop debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a095-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3a095-109">Remarks</span></span>  
 <span data-ttu-id="3a095-110">Wenn der Debugger eine just-in-Time (JIT)-Kompilierung, die keine entsprechende Zuordnung in die Microsoft intermediate Language (MSIL) aufweist findet, hält der Ausführung an, wenn die Angabe dieses Typs von nicht zugeordnetem Code Flag festgelegt wurde; Andernfalls wird die transparente schrittweise Ausführung fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="3a095-110">When the debugger finds a just-in-time (JIT) compilation that has no corresponding mapping to Microsoft intermediate language (MSIL), it halts execution if the flag specifying that type of unmapped code has been set; otherwise, stepping transparently continues.</span></span>  
  
 <span data-ttu-id="3a095-111">Wenn der Debugger eine zugeordnetem eingeben eine Methode verwendet, wird nicht es unbedingt nicht zugeordnetem Code überspringen.</span><span class="sxs-lookup"><span data-stu-id="3a095-111">If the debugger doesn't use a stepper to enter a method, then it won't necessarily step over unmapped code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a095-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3a095-112">Requirements</span></span>  
 <span data-ttu-id="3a095-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a095-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a095-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3a095-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3a095-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a095-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a095-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a095-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
