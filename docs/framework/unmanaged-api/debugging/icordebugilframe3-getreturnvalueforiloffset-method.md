---
title: ICorDebugILFrame3::GetReturnValueForILOffset-Methode
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
api_name:
- ICorDebugILFrame3.GetReturnValueForILOffset
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 06522727-5f64-4391-9331-11386883c352
topic_type:
- apiref
ms.openlocfilehash: 11207298b071527151535144330790df767c2101
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725000"
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a><span data-ttu-id="ca73f-102">ICorDebugILFrame3::GetReturnValueForILOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="ca73f-102">ICorDebugILFrame3::GetReturnValueForILOffset Method</span></span>

<span data-ttu-id="ca73f-103">Ruft ein ICorDebug Value-Objekt ab, das den Rückgabewert einer Funktion kapselt.</span><span class="sxs-lookup"><span data-stu-id="ca73f-103">Gets an "ICorDebugValue" object that encapsulates the return value of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca73f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ca73f-104">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca73f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ca73f-105">Parameters</span></span>  

 `ILOffset`  
 <span data-ttu-id="ca73f-106">Der IL-Offset.</span><span class="sxs-lookup"><span data-stu-id="ca73f-106">The IL offset.</span></span> <span data-ttu-id="ca73f-107">Weitere Informationen finden Sie im Abschnitt mit den Hinweisen.</span><span class="sxs-lookup"><span data-stu-id="ca73f-107">See the Remarks section.</span></span>  
  
 `ppReturnValue`  
 <span data-ttu-id="ca73f-108">Ein Zeiger auf die Adresse eines ICorDebugValue-Schnittstellen Objekts, das Informationen über den Rückgabewert eines Funktions Aufrufes bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ca73f-108">A pointer to the address of an "ICorDebugValue" interface object that provides information about the return value of a function call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca73f-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ca73f-109">Remarks</span></span>  

 <span data-ttu-id="ca73f-110">Diese Methode wird zusammen mit der [ICorDebugCode3:: getreturnvalueliveoffset](icordebugcode3-getreturnvalueliveoffset-method.md) -Methode verwendet, um den Rückgabewert einer Methode zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ca73f-110">This method is used along with the [ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) method to get the return value of a method.</span></span> <span data-ttu-id="ca73f-111">Dies ist für Methoden sehr nützlich, deren Rückgabewerte ignoriert wurden, wie in den folgenden beiden Codebeispielen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ca73f-111">It is particularly useful in the case of methods whose return values are ignored, as in the following two code examples.</span></span> <span data-ttu-id="ca73f-112">Im ersten Beispiel wird die <xref:System.Int32.TryParse%2A?displayProperty=nameWithType>-Methode aufgerufen, der Rückgabewert der Methode jedoch ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ca73f-112">The first example calls the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method, but ignores the method's return value.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 <span data-ttu-id="ca73f-113">Das zweite Beispiel veranschaulicht ein allgemeineres Problem beim Debuggen.</span><span class="sxs-lookup"><span data-stu-id="ca73f-113">The second example illustrates a much more common problem in debugging.</span></span> <span data-ttu-id="ca73f-114">Da eine Methode als Argument eines Methodenaufrufs verwendet wird, kann auf den Rückgabewert nur dann zugegriffen werden, wenn der Debugger in Einzelschritten in der aufgerufenen Methode bewegt wird.</span><span class="sxs-lookup"><span data-stu-id="ca73f-114">Because a method is used as an argument in a method call, its return value is accessible only when the debugger steps through the called method.</span></span> <span data-ttu-id="ca73f-115">In vielen Fällen ist dies nicht möglich, insbesondere wenn die aufgerufene Methode in einer externen Bibliothek definiert ist.</span><span class="sxs-lookup"><span data-stu-id="ca73f-115">In many cases, particularly when the called method is defined in an external library, that is not possible.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 <span data-ttu-id="ca73f-116">Wenn Sie die [ICorDebugCode3:: getreturnvalueliveoffset](icordebugcode3-getreturnvalueliveoffset-method.md) -Methode einem IL-Offset an eine Funktions Aufrufsite übergeben, wird mindestens ein System eigenes Offset zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ca73f-116">If you pass the [ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) method an IL offset to a function call site, it returns one or more native offsets.</span></span> <span data-ttu-id="ca73f-117">In diesem Fall kann der Debugger Haltepunkte für diese systemeigenen Offsets in der Funktion festlegen.</span><span class="sxs-lookup"><span data-stu-id="ca73f-117">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="ca73f-118">Wenn der Debugger auf einen der Haltepunkte trifft, können Sie den gleichen IL-Offset übergeben, den Sie an diese Methode übergeben haben, um den Rückgabewert abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ca73f-118">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to get the return value.</span></span> <span data-ttu-id="ca73f-119">Der Debugger sollte dann alle von ihm festgelegten Haltepunkte entfernen.</span><span class="sxs-lookup"><span data-stu-id="ca73f-119">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="ca73f-120">Die [ICorDebugCode3:: getreturnvalueliveoffset-Methode](icordebugcode3-getreturnvalueliveoffset-method.md) und- `ICorDebugILFrame3::GetReturnValueForILOffset` Methoden ermöglichen es Ihnen, Rückgabewert Informationen nur für Verweis Typen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ca73f-120">The [ICorDebugCode3::GetReturnValueLiveOffset Method](icordebugcode3-getreturnvalueliveoffset-method.md) and `ICorDebugILFrame3::GetReturnValueForILOffset` methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="ca73f-121">Das Abrufen von Rückgabewertinformationen für Werttypen wird nicht unterstützt (alle Typen, die von <xref:System.ValueType> abgeleitet werden).</span><span class="sxs-lookup"><span data-stu-id="ca73f-121">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="ca73f-122">Der durch den-Parameter angegebene IL `ILOffset` -Offset sollte sich an einer Funktions Aufrufsite befinden, und die zu debuggende Komponente sollte an einem Haltepunkt angehalten werden, der bei dem systemeigenen Offset festgelegt ist, der von der [ICorDebugCode3:: getreturnvalueliveoffset](icordebugcode3-getreturnvalueliveoffset-method.md) -Methode für denselben IL-Offset</span><span class="sxs-lookup"><span data-stu-id="ca73f-122">The IL offset specified by the `ILOffset` parameter should be at a function call site, and the debuggee should be stopped at a breakpoint set at the native offset returned by the [ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) method for the same IL offset.</span></span> <span data-ttu-id="ca73f-123">Wenn die zu debuggende Komponente nicht an der korrekten Position für den festgelegten IL-Offset angehalten wird, schlägt die API fehl.</span><span class="sxs-lookup"><span data-stu-id="ca73f-123">If the debuggee is not stopped at the correct location for the specified IL offset, the API will fail.</span></span>  
  
 <span data-ttu-id="ca73f-124">Wenn der Funktionsaufruf keinen Wert zurückgibt, schlägt die API fehl.</span><span class="sxs-lookup"><span data-stu-id="ca73f-124">If the function call doesn't return a value, the API will fail.</span></span>  
  
 <span data-ttu-id="ca73f-125">Die `ICorDebugILFrame3::GetReturnValueForILOffset`-Methode ist nur auf x86- und AMD64-basierten Systemen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ca73f-125">The `ICorDebugILFrame3::GetReturnValueForILOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca73f-126">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ca73f-126">Requirements</span></span>  

 <span data-ttu-id="ca73f-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca73f-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca73f-128">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca73f-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca73f-129">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca73f-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca73f-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca73f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca73f-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ca73f-131">See also</span></span>

- [<span data-ttu-id="ca73f-132">GetReturnValueLiveOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="ca73f-132">GetReturnValueLiveOffset Method</span></span>](icordebugcode3-getreturnvalueliveoffset-method.md)
- [<span data-ttu-id="ca73f-133">ICorDebugILFrame3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ca73f-133">ICorDebugILFrame3 Interface</span></span>](icordebugilframe3-interface.md)
