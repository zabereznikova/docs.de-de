---
title: ICorDebugStepper::SetUnmappedStopMask-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.SetUnmappedStopMask
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::SetUnmappedStopMask
helpviewer_keywords:
- ICorDebugStepper::SetUnmappedStopMask method [.NET Framework debugging]
- SetUnmappedStopMask method [.NET Framework debugging]
ms.assetid: b1211981-e90c-4e05-8def-fa18d85ad9ab
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 163a26ff38d0a4bbae5710d6d841ea29682a8984
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a><span data-ttu-id="2da82-102">ICorDebugStepper::SetUnmappedStopMask-Methode</span><span class="sxs-lookup"><span data-stu-id="2da82-102">ICorDebugStepper::SetUnmappedStopMask Method</span></span>
<span data-ttu-id="2da82-103">Legt einen Wert, der den Typ des nicht zugeordneten Codes angibt, in dem die Ausführung angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="2da82-103">Sets a value that specifies the type of unmapped code in which execution will halt.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2da82-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2da82-104">Syntax</span></span>  
  
```  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2da82-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2da82-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="2da82-106">[in] Der Wert der CorDebugUnmappedStop-Enumeration, die den Typ des nicht zugeordneten Codes angibt, in dem der Debugger die Ausführung angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="2da82-106">[in] A value of the CorDebugUnmappedStop enumeration that specifies the type of unmapped code in which the debugger will halt execution.</span></span>  
  
 <span data-ttu-id="2da82-107">Der Standardwert ist STOP_OTHER_UNMAPPED.</span><span class="sxs-lookup"><span data-stu-id="2da82-107">The default value is STOP_OTHER_UNMAPPED.</span></span> <span data-ttu-id="2da82-108">Der Wert STOP_UNMANAGED ist nur gültig, wenn Interop-Debuggen.</span><span class="sxs-lookup"><span data-stu-id="2da82-108">The value STOP_UNMANAGED is only valid with interop debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2da82-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2da82-109">Remarks</span></span>  
 <span data-ttu-id="2da82-110">Wenn der Debugger eine just-in-Time (JIT)-Kompilierung, die keine entsprechende Zuordnung in die Microsoft intermediate Language (MSIL) aufweist findet, hält der Ausführung an, wenn die Angabe dieses Typs von nicht zugeordnetem Code Flag festgelegt wurde; Andernfalls wird die transparente schrittweise Ausführung fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="2da82-110">When the debugger finds a just-in-time (JIT) compilation that has no corresponding mapping to Microsoft intermediate language (MSIL), it halts execution if the flag specifying that type of unmapped code has been set; otherwise, stepping transparently continues.</span></span>  
  
 <span data-ttu-id="2da82-111">Wenn der Debugger eine zugeordnetem eingeben eine Methode verwendet, wird nicht es unbedingt nicht zugeordnetem Code überspringen.</span><span class="sxs-lookup"><span data-stu-id="2da82-111">If the debugger doesn't use a stepper to enter a method, then it won't necessarily step over unmapped code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2da82-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2da82-112">Requirements</span></span>  
 <span data-ttu-id="2da82-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2da82-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2da82-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2da82-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2da82-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2da82-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2da82-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2da82-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
