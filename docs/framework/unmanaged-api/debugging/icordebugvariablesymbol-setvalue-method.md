---
title: 'Icordebugvariablesymbol:: SetValue-Methode'
ms.date: 03/30/2017
ms.assetid: 4609418d-71fa-44bc-9618-4d529d25cabb
ms.openlocfilehash: fbd3d617e3448730241ccfda7bd26b65d17b694d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121882"
---
# <a name="icordebugvariablesymbolsetvalue-method"></a><span data-ttu-id="90768-102">Icordebugvariablesymbol:: SetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="90768-102">ICorDebugVariableSymbol::SetValue Method</span></span>
<span data-ttu-id="90768-103">Weist einer Variablen den Wert eines Bytearrays zu.</span><span class="sxs-lookup"><span data-stu-id="90768-103">Assigns the value of a byte array to a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90768-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="90768-104">Syntax</span></span>  
  
```cpp  
HRESULT SetValue(  
   [in] ULONG32 offset,  
   [in] DWORD threadID,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [in, size_is(cbValue)] BYTE pValue[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90768-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="90768-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="90768-106">[in] Der Startoffset in der Variablen, an dem der Wert festgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="90768-106">[in] The starting offset in the variable at which to set the value.</span></span> <span data-ttu-id="90768-107">Dieser Parameter wird verwendet, wenn in Memberfelder in einem Objekt geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="90768-107">This parameter is used when writing to member fields in an object.</span></span>  
  
 `threadID`  
 <span data-ttu-id="90768-108">[in] Der Threadbezeichner des Threads, dessen Kontext aktualisiert werden muss, damit der neue Wert berücksichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="90768-108">[in] The thread identifier of the thread whose context must be updated to reflect the new value.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="90768-109">[in] Die Größe des Threadkontexts in Byte.</span><span class="sxs-lookup"><span data-stu-id="90768-109">[in] The size in bytes of the thread context.</span></span>  
  
 `context`  
 <span data-ttu-id="90768-110">[in] Der Threadkontext, der zum Schreiben des Werts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="90768-110">[in] The thread context used to write the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="90768-111">[in] Die Größe des `pValue`-Puffers in Byte.</span><span class="sxs-lookup"><span data-stu-id="90768-111">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="90768-112">[in] Der Puffer, der den festzulegenden Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="90768-112">[in] The buffer that contains the value to set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90768-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="90768-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="90768-114">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="90768-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90768-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="90768-115">Requirements</span></span>  
 <span data-ttu-id="90768-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90768-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90768-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90768-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90768-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90768-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90768-119">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90768-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90768-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90768-120">See also</span></span>

- [<span data-ttu-id="90768-121">ICorDebugVariableSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="90768-121">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="90768-122">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="90768-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
