---
title: ICorDebugVariableSymbol::GetSize-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4609418d-71fa-44bc-9618-4d529d25cabb
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 12c13259d20301b0f485a6041fa884b0996cbbdc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablesymbolsetvalue-method"></a><span data-ttu-id="f4179-102">ICorDebugVariableSymbol::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="f4179-102">ICorDebugVariableSymbol::SetValue Method</span></span>
<span data-ttu-id="f4179-103">Weist einer Variablen den Wert eines Bytearrays zu.</span><span class="sxs-lookup"><span data-stu-id="f4179-103">Assigns the value of a byte array to a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4179-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f4179-104">Syntax</span></span>  
  
```  
HRESULT SetValue(  
   [in] ULONG32 offset,  
   [in] DWORD threadID,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [in, size_is(cbValue)] BYTE pValue[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f4179-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f4179-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="f4179-106">[in] Der Startoffset in der Variablen, an dem der Wert festgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f4179-106">[in] The starting offset in the variable at which to set the value.</span></span> <span data-ttu-id="f4179-107">Dieser Parameter wird verwendet, wenn in Memberfelder in einem Objekt geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="f4179-107">This parameter is used when writing to member fields in an object.</span></span>  
  
 `threadID`  
 <span data-ttu-id="f4179-108">[in] Der Threadbezeichner des Threads, dessen Kontext aktualisiert werden muss, damit der neue Wert berücksichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="f4179-108">[in] The thread identifier of the thread whose context must be updated to reflect the new value.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="f4179-109">[in] Die Größe des Threadkontexts in Byte.</span><span class="sxs-lookup"><span data-stu-id="f4179-109">[in] The size in bytes of the thread context.</span></span>  
  
 `context`  
 <span data-ttu-id="f4179-110">[in] Der Threadkontext, der zum Schreiben des Werts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f4179-110">[in] The thread context used to write the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="f4179-111">[in] Die Größe des `pValue`-Puffers in Byte.</span><span class="sxs-lookup"><span data-stu-id="f4179-111">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="f4179-112">[in] Der Puffer, der den festzulegenden Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="f4179-112">[in] The buffer that contains the value to set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4179-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f4179-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4179-114">Diese Methode ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f4179-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4179-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f4179-115">Requirements</span></span>  
 <span data-ttu-id="f4179-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4179-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4179-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4179-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4179-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4179-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4179-119">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4179-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4179-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4179-120">See Also</span></span>  
 [<span data-ttu-id="f4179-121">ICorDebugVariableSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f4179-121">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [<span data-ttu-id="f4179-122">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f4179-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
