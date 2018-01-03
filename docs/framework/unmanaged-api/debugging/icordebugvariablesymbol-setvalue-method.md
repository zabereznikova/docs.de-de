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
ms.workload: dotnet
ms.openlocfilehash: 2433274c2b8fa3ac547696c03a0d0e25c8b63082
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablesymbolsetvalue-method"></a><span data-ttu-id="5013e-102">ICorDebugVariableSymbol::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="5013e-102">ICorDebugVariableSymbol::SetValue Method</span></span>
<span data-ttu-id="5013e-103">Weist einer Variablen den Wert eines Bytearrays zu.</span><span class="sxs-lookup"><span data-stu-id="5013e-103">Assigns the value of a byte array to a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5013e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5013e-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="5013e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5013e-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="5013e-106">[in] Der Startoffset in der Variablen, an dem der Wert festgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5013e-106">[in] The starting offset in the variable at which to set the value.</span></span> <span data-ttu-id="5013e-107">Dieser Parameter wird verwendet, wenn in Memberfelder in einem Objekt geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="5013e-107">This parameter is used when writing to member fields in an object.</span></span>  
  
 `threadID`  
 <span data-ttu-id="5013e-108">[in] Der Threadbezeichner des Threads, dessen Kontext aktualisiert werden muss, damit der neue Wert berücksichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="5013e-108">[in] The thread identifier of the thread whose context must be updated to reflect the new value.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="5013e-109">[in] Die Größe des Threadkontexts in Byte.</span><span class="sxs-lookup"><span data-stu-id="5013e-109">[in] The size in bytes of the thread context.</span></span>  
  
 `context`  
 <span data-ttu-id="5013e-110">[in] Der Threadkontext, der zum Schreiben des Werts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5013e-110">[in] The thread context used to write the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="5013e-111">[in] Die Größe des `pValue`-Puffers in Byte.</span><span class="sxs-lookup"><span data-stu-id="5013e-111">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="5013e-112">[in] Der Puffer, der den festzulegenden Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="5013e-112">[in] The buffer that contains the value to set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5013e-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5013e-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5013e-114">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5013e-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5013e-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5013e-115">Requirements</span></span>  
 <span data-ttu-id="5013e-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5013e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5013e-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5013e-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5013e-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5013e-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5013e-119">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5013e-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5013e-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5013e-120">See Also</span></span>  
 [<span data-ttu-id="5013e-121">ICorDebugVariableSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5013e-121">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [<span data-ttu-id="5013e-122">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5013e-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
