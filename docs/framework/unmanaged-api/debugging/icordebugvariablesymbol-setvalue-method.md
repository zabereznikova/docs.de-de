---
title: ICorDebugVariableSymbol::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: 4609418d-71fa-44bc-9618-4d529d25cabb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5bfbadc5553e86b2db10d66298c8d24d2a0f8bde
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946171"
---
# <a name="icordebugvariablesymbolsetvalue-method"></a><span data-ttu-id="6e226-102">ICorDebugVariableSymbol::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="6e226-102">ICorDebugVariableSymbol::SetValue Method</span></span>
<span data-ttu-id="6e226-103">Weist einer Variablen den Wert eines Bytearrays zu.</span><span class="sxs-lookup"><span data-stu-id="6e226-103">Assigns the value of a byte array to a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e226-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6e226-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="6e226-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6e226-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="6e226-106">[in] Der Startoffset in der Variablen, an dem der Wert festgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6e226-106">[in] The starting offset in the variable at which to set the value.</span></span> <span data-ttu-id="6e226-107">Dieser Parameter wird verwendet, wenn in Memberfelder in einem Objekt geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="6e226-107">This parameter is used when writing to member fields in an object.</span></span>  
  
 `threadID`  
 <span data-ttu-id="6e226-108">[in] Der Threadbezeichner des Threads, dessen Kontext aktualisiert werden muss, damit der neue Wert berücksichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="6e226-108">[in] The thread identifier of the thread whose context must be updated to reflect the new value.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="6e226-109">[in] Die Größe des Threadkontexts in Byte.</span><span class="sxs-lookup"><span data-stu-id="6e226-109">[in] The size in bytes of the thread context.</span></span>  
  
 `context`  
 <span data-ttu-id="6e226-110">[in] Der Threadkontext, der zum Schreiben des Werts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6e226-110">[in] The thread context used to write the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="6e226-111">[in] Die Größe des `pValue`-Puffers in Byte.</span><span class="sxs-lookup"><span data-stu-id="6e226-111">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="6e226-112">[in] Der Puffer, der den festzulegenden Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="6e226-112">[in] The buffer that contains the value to set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e226-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6e226-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6e226-114">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6e226-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e226-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6e226-115">Requirements</span></span>  
 <span data-ttu-id="6e226-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e226-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e226-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6e226-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6e226-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e226-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e226-119">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e226-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e226-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e226-120">See also</span></span>

- [<span data-ttu-id="6e226-121">ICorDebugVariableSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e226-121">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="6e226-122">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6e226-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
