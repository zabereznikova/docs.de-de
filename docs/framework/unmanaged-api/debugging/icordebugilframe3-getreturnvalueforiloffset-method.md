---
title: ICorDebugILFrame3::GetReturnValueForILOffset-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- csharp
- vb
api_name: ICorDebugILFrame3.GetReturnValueForILOffset
api_location: mscordbi.dll
api_type: COM
ms.assetid: 06522727-5f64-4391-9331-11386883c352
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c58319de99bdd8d7cce0ea55ccb3140a31a39bd0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a><span data-ttu-id="c4b35-102">ICorDebugILFrame3::GetReturnValueForILOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="c4b35-102">ICorDebugILFrame3::GetReturnValueForILOffset Method</span></span>
<span data-ttu-id="c4b35-103">Ruft ein "ICorDebugValue"-Objekt, das den Rückgabewert einer Funktion kapselt.</span><span class="sxs-lookup"><span data-stu-id="c4b35-103">Gets an "ICorDebugValue" object that encapsulates the return value of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4b35-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4b35-104">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,   
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c4b35-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c4b35-105">Parameters</span></span>  
 `ILOffset`  
 <span data-ttu-id="c4b35-106">Der IL-Offset.</span><span class="sxs-lookup"><span data-stu-id="c4b35-106">The IL offset.</span></span> <span data-ttu-id="c4b35-107">Weitere Informationen finden Sie im Abschnitt "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="c4b35-107">See the Remarks section.</span></span>  
  
 `ppReturnValue`  
 <span data-ttu-id="c4b35-108">Ein Zeiger auf die Adresse der Schnittstelle "ICorDebugValue"-Objekts, das Informationen über den Rückgabewert eines Funktionsaufrufs bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="c4b35-108">A pointer to the address of an "ICorDebugValue" interface object that provides information about the return value of a function call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4b35-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c4b35-109">Remarks</span></span>  
 <span data-ttu-id="c4b35-110">Diese Methode wird verwendet, zusammen mit den [icordebugcode3:: Getreturnvalueliveoffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) Methode, um den Rückgabewert einer Methode abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c4b35-110">This method is used along with the [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) method to get the return value of a method.</span></span> <span data-ttu-id="c4b35-111">Dies ist für Methoden sehr nützlich, deren Rückgabewerte ignoriert wurden, wie in den folgenden beiden Codebeispielen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c4b35-111">It is particularly useful in the case of methods whose return values are ignored, as in the following two code examples.</span></span> <span data-ttu-id="c4b35-112">Im ersten Beispiel wird die <xref:System.Int32.TryParse%2A?displayProperty=nameWithType>-Methode aufgerufen, der Rückgabewert der Methode jedoch ignoriert.</span><span class="sxs-lookup"><span data-stu-id="c4b35-112">The first example calls the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method, but ignores the method's return value.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 <span data-ttu-id="c4b35-113">Das zweite Beispiel veranschaulicht ein allgemeineres Problem beim Debuggen.</span><span class="sxs-lookup"><span data-stu-id="c4b35-113">The second example illustrates a much more common problem in debugging.</span></span> <span data-ttu-id="c4b35-114">Da eine Methode als Argument eines Methodenaufrufs verwendet wird, kann auf den Rückgabewert nur dann zugegriffen werden, wenn der Debugger in Einzelschritten in der aufgerufenen Methode bewegt wird.</span><span class="sxs-lookup"><span data-stu-id="c4b35-114">Because a method is used as an argument in a method call, its return value is accessible only when the debugger steps through the called method.</span></span> <span data-ttu-id="c4b35-115">In vielen Fällen ist dies nicht möglich, insbesondere wenn die aufgerufene Methode in einer externen Bibliothek definiert ist.</span><span class="sxs-lookup"><span data-stu-id="c4b35-115">In many cases, particularly when the called method is defined in an external library, that is not possible.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 <span data-ttu-id="c4b35-116">Wenn Sie übergeben die [icordebugcode3:: Getreturnvalueliveoffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) -Methode ein IL-Offsets an eine funktionsaufrufsite, gibt eine oder mehrere systemeigene Offsets zurück.</span><span class="sxs-lookup"><span data-stu-id="c4b35-116">If you pass the [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) method an IL offset to a function call site, it returns one or more native offsets.</span></span> <span data-ttu-id="c4b35-117">In diesem Fall kann der Debugger Haltepunkte für diese systemeigenen Offsets in der Funktion festlegen.</span><span class="sxs-lookup"><span data-stu-id="c4b35-117">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="c4b35-118">Wenn der Debugger auf einen der Haltepunkte trifft, können Sie den gleichen IL-Offset übergeben, den Sie an diese Methode übergeben haben, um den Rückgabewert abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c4b35-118">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to get the return value.</span></span> <span data-ttu-id="c4b35-119">Der Debugger sollte dann alle von ihm festgelegten Haltepunkte entfernen.</span><span class="sxs-lookup"><span data-stu-id="c4b35-119">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="c4b35-120">Die [icordebugcode3:: Getreturnvalueliveoffset-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) und `ICorDebugILFrame3::GetReturnValueForILOffset` Methoden ermöglichen es Ihnen, Rückgabewertinformationen nur für Verweistypen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c4b35-120">The [ICorDebugCode3::GetReturnValueLiveOffset Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) and `ICorDebugILFrame3::GetReturnValueForILOffset` methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="c4b35-121">Das Abrufen von Rückgabewertinformationen für Werttypen wird nicht unterstützt (alle Typen, die von <xref:System.ValueType> abgeleitet werden).</span><span class="sxs-lookup"><span data-stu-id="c4b35-121">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="c4b35-122">Der IL-Offset gemäß der `ILOffset` Parameter sollte eine funktionsaufrufsite sein und die zu debuggende Komponente sollte an einen Haltepunkt festgelegt haben, beim systemeigenen Offset zurückgegebenes angehalten werden die [icordebugcode3:: Getreturnvalueliveoffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) Methode für den identischen IL-Offset.</span><span class="sxs-lookup"><span data-stu-id="c4b35-122">The IL offset specified by the `ILOffset` parameter should be at a function call site, and the debuggee should be stopped at a breakpoint set at the native offset returned by the [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) method for the same IL offset.</span></span> <span data-ttu-id="c4b35-123">Wenn die zu debuggende Komponente nicht an der korrekten Position für den festgelegten IL-Offset angehalten wird, schlägt die API fehl.</span><span class="sxs-lookup"><span data-stu-id="c4b35-123">If the debuggee is not stopped at the correct location for the specified IL offset, the API will fail.</span></span>  
  
 <span data-ttu-id="c4b35-124">Wenn der Funktionsaufruf keinen Wert zurückgibt, schlägt die API fehl.</span><span class="sxs-lookup"><span data-stu-id="c4b35-124">If the function call doesn't return a value, the API will fail.</span></span>  
  
 <span data-ttu-id="c4b35-125">Die `ICorDebugILFrame3::GetReturnValueForILOffset`-Methode ist nur auf x86- und AMD64-basierten Systemen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c4b35-125">The `ICorDebugILFrame3::GetReturnValueForILOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4b35-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c4b35-126">Requirements</span></span>  
 <span data-ttu-id="c4b35-127">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4b35-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4b35-128">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4b35-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4b35-129">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4b35-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4b35-130">**.NET Framework-Versionen:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4b35-130">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4b35-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4b35-131">See Also</span></span>  
 [<span data-ttu-id="c4b35-132">GetReturnValueLiveOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="c4b35-132">GetReturnValueLiveOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)  
 [<span data-ttu-id="c4b35-133">ICorDebugILFrame3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c4b35-133">ICorDebugILFrame3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)
