---
title: ICorDebugVariableSymbol::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: 90abece1-392e-4ade-94a1-30c75b0f7074
ms.openlocfilehash: 2dc074384d209d0740a1fb0a9a16d96ff355f02b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790883"
---
# <a name="icordebugvariablesymbolgetvalue-method"></a><span data-ttu-id="ff352-102">ICorDebugVariableSymbol::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="ff352-102">ICorDebugVariableSymbol::GetValue Method</span></span>
<span data-ttu-id="ff352-103">Ruft den Wert einer Variablen als Bytearray ab.</span><span class="sxs-lookup"><span data-stu-id="ff352-103">Gets the value of a variable as a byte array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff352-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ff352-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="ff352-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="ff352-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="ff352-106">[in] Der Startoffset in der Variablen, aus der der Wert gelesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="ff352-106">[in] The starting offset in the variable from which to read the value.</span></span> <span data-ttu-id="ff352-107">Dieser Parameter wird beim Lesen von Memberfeldern in einem Objekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="ff352-107">This parameter is used when reading member fields in an object.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="ff352-108">[in] Die Größe des `context`-Arguments in Byte.</span><span class="sxs-lookup"><span data-stu-id="ff352-108">[in] The size in bytes of the `context` argument.</span></span>  
  
 `context`  
 <span data-ttu-id="ff352-109">[in] Der zum Lesen des Werts verwendete Threadkontext.</span><span class="sxs-lookup"><span data-stu-id="ff352-109">[in] The thread context used to read the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="ff352-110">[in] Die Größe des `pValue`-Puffers in Byte.</span><span class="sxs-lookup"><span data-stu-id="ff352-110">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pcbValue`  
 <span data-ttu-id="ff352-111">[out] Die Anzahl der tatsächlich in den `pValue`-Puffer geschriebenen Bytes.</span><span class="sxs-lookup"><span data-stu-id="ff352-111">[out] The number of bytes actually written to the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="ff352-112">[out] Ein Bytearray, das den Wert der Variablen enthält.</span><span class="sxs-lookup"><span data-stu-id="ff352-112">[out] A byte array that contains the value of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff352-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ff352-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ff352-114">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ff352-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff352-115">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ff352-115">Requirements</span></span>  
 <span data-ttu-id="ff352-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff352-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff352-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ff352-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ff352-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff352-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff352-119">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff352-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff352-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff352-120">See also</span></span>

- [<span data-ttu-id="ff352-121">ICorDebugVariableSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ff352-121">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="ff352-122">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ff352-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
