---
title: 'Icordebugvariablesymbol:: GetValue-Methode'
ms.date: 03/30/2017
ms.assetid: 90abece1-392e-4ade-94a1-30c75b0f7074
ms.openlocfilehash: 5ef7e67efb2bafd9b9f52203246fd7d1590e6107
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120963"
---
# <a name="icordebugvariablesymbolgetvalue-method"></a><span data-ttu-id="9253d-102">Icordebugvariablesymbol:: GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="9253d-102">ICorDebugVariableSymbol::GetValue Method</span></span>
<span data-ttu-id="9253d-103">Ruft den Wert einer Variablen als Bytearray ab.</span><span class="sxs-lookup"><span data-stu-id="9253d-103">Gets the value of a variable as a byte array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9253d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9253d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue(  
   [in] ULONG32 offset,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [out] ULONG32 *pcbValue,  
   [out, size_is(cbValue), length_is(*pcbValue)] BYTE pValue[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9253d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9253d-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="9253d-106">[in] Der Startoffset in der Variablen, aus der der Wert gelesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="9253d-106">[in] The starting offset in the variable from which to read the value.</span></span> <span data-ttu-id="9253d-107">Dieser Parameter wird beim Lesen von Memberfeldern in einem Objekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="9253d-107">This parameter is used when reading member fields in an object.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="9253d-108">[in] Die Größe des `context`-Arguments in Byte.</span><span class="sxs-lookup"><span data-stu-id="9253d-108">[in] The size in bytes of the `context` argument.</span></span>  
  
 `context`  
 <span data-ttu-id="9253d-109">[in] Der zum Lesen des Werts verwendete Threadkontext.</span><span class="sxs-lookup"><span data-stu-id="9253d-109">[in] The thread context used to read the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="9253d-110">[in] Die Größe des `pValue`-Puffers in Byte.</span><span class="sxs-lookup"><span data-stu-id="9253d-110">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pcbValue`  
 <span data-ttu-id="9253d-111">[out] Die Anzahl der tatsächlich in den `pValue`-Puffer geschriebenen Bytes.</span><span class="sxs-lookup"><span data-stu-id="9253d-111">[out] The number of bytes actually written to the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="9253d-112">[out] Ein Bytearray, das den Wert der Variablen enthält.</span><span class="sxs-lookup"><span data-stu-id="9253d-112">[out] A byte array that contains the value of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9253d-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9253d-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9253d-114">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9253d-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9253d-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9253d-115">Requirements</span></span>  
 <span data-ttu-id="9253d-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9253d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9253d-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9253d-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9253d-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9253d-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9253d-119">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9253d-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9253d-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9253d-120">See also</span></span>

- [<span data-ttu-id="9253d-121">ICorDebugVariableSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9253d-121">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="9253d-122">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9253d-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
