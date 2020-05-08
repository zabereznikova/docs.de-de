---
title: ICorDebugCode3::GetReturnValueLiveOffset-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugCode3.GetReturnValueLiveOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset
helpviewer_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset method [.NET Framework debugging]
- GetReturnValueLiveOffset method [.NET Framework debugging]
ms.assetid: 8c2ff5d8-8c04-4423-b1e1-e1c8764b36d3
topic_type:
- apiref
ms.openlocfilehash: 2cb4c79601061ab8473d6d7ca50c4ed2f92b01c4
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893429"
---
# <a name="icordebugcode3getreturnvalueliveoffset-method"></a><span data-ttu-id="8a014-102">ICorDebugCode3::GetReturnValueLiveOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="8a014-102">ICorDebugCode3::GetReturnValueLiveOffset Method</span></span>
<span data-ttu-id="8a014-103">Ruft während eines festgelegten IL-Offsets die systemeigenen Offsets ab, in denen ein Haltepunkt eingefügt werden sollte, damit der Debugger den Rückgabewert aus einer Funktion abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="8a014-103">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a014-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8a014-104">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueLiveOffset(  
    [in] ULONG32 ILoffset,  
    [in] ULONG32 bufferSize,
    [out] ULONG32 *pFetched,
    [out, size_is(buffersize), length_is(*pFetched)] ULong32 pOffsets[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a014-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8a014-105">Parameters</span></span>  
 `ILoffset`  
 <span data-ttu-id="8a014-106">Der IL-Offset.</span><span class="sxs-lookup"><span data-stu-id="8a014-106">The IL offset.</span></span> <span data-ttu-id="8a014-107">Es muss sich um eine Funktionsaufrufsite handeln, andernfalls schlägt der Funktionsaufruf fehl.</span><span class="sxs-lookup"><span data-stu-id="8a014-107">It must be a function call site or the function call will fail.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="8a014-108">Die Anzahl der zum Speichern von `pOffsets` verfügbaren Bytes.</span><span class="sxs-lookup"><span data-stu-id="8a014-108">The number of bytes available to store `pOffsets`.</span></span>  
  
 `pFetched`  
 <span data-ttu-id="8a014-109">Ein Zeiger auf die Anzahl der tatsächlich zurückgegebenen Offsets.</span><span class="sxs-lookup"><span data-stu-id="8a014-109">A pointer to the number of offsets actually returned.</span></span> <span data-ttu-id="8a014-110">Normalerweise ist dies der Wert 1, eine einzelne IL-Anweisung kann jedoch mehrere `CALL`-Assemblyanweisungen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="8a014-110">Usually, its value is 1, but a single IL instruction can map to multiple `CALL` assembly instructions.</span></span>  
  
 `pOffsets`  
 <span data-ttu-id="8a014-111">Ein Array systemeigener Offsets.</span><span class="sxs-lookup"><span data-stu-id="8a014-111">An array of native offsets.</span></span> <span data-ttu-id="8a014-112">Normalerweise enthält `pOffsets` einen einzelnen Offset, obwohl eine einzelne IL-Anweisung mehreren `CALL`-Assemblyanweisungen zugeordnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="8a014-112">Typically, `pOffsets` contains a single offset, although a single IL instruction can map to multiple map to multiple `CALL` assembly instructions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a014-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8a014-113">Remarks</span></span>  
 <span data-ttu-id="8a014-114">Diese Methode wird zusammen mit der [ICorDebugILFrame3:: getreturnvalueforiloffset](icordebugilframe3-getreturnvalueforiloffset-method.md) -Methode verwendet, um den Rückgabewert einer Methode, die einen Verweistyp zurückgibt, zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8a014-114">This method is used along with the [ICorDebugILFrame3::GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value of a method that returns a reference type.</span></span> <span data-ttu-id="8a014-115">Durch die Übergabe eines IL-Offsets an eine Funktionsaufrufsite für diese Methode wird mindestens ein systemeigener Offset zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8a014-115">Passing an IL offset to a function call site to this method returns one or more native offsets.</span></span> <span data-ttu-id="8a014-116">In diesem Fall kann der Debugger Haltepunkte für diese systemeigenen Offsets in der Funktion festlegen.</span><span class="sxs-lookup"><span data-stu-id="8a014-116">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="8a014-117">Wenn der Debugger auf einen der Breakpoints trifft, können Sie denselben IL-Offset übergeben, den Sie an diese Methode übergeben haben, an die [ICorDebugILFrame3:: getreturnvalueforiloffset](icordebugilframe3-getreturnvalueforiloffset-method.md) -Methode, um den Rückgabewert zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8a014-117">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to the [ICorDebugILFrame3::GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value.</span></span> <span data-ttu-id="8a014-118">Der Debugger sollte dann alle von ihm festgelegten Haltepunkte entfernen.</span><span class="sxs-lookup"><span data-stu-id="8a014-118">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="8a014-119">Die `ICorDebugCode3::GetReturnValueLiveOffset` -Methode und die [ICorDebugILFrame3:: getreturnvalueforiloffset](icordebugilframe3-getreturnvalueforiloffset-method.md) -Methode ermöglichen es Ihnen, Rückgabewert Informationen nur für Verweis Typen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8a014-119">The `ICorDebugCode3::GetReturnValueLiveOffset` and [ICorDebugILFrame3::GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="8a014-120">Das Abrufen von Rückgabewertinformationen für Werttypen wird nicht unterstützt (alle Typen, die von <xref:System.ValueType> abgeleitet werden).</span><span class="sxs-lookup"><span data-stu-id="8a014-120">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="8a014-121">Die Funktion gibt die `HRESULT`-Werte zurück, die in der folgenden Tabelle dargestellt sind.</span><span class="sxs-lookup"><span data-stu-id="8a014-121">The function returns the `HRESULT` values shown in the following table.</span></span>  
  
|<span data-ttu-id="8a014-122">`HRESULT`-Wert</span><span class="sxs-lookup"><span data-stu-id="8a014-122">`HRESULT` value</span></span>|<span data-ttu-id="8a014-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8a014-123">Description</span></span>|  
|---------------------|-----------------|  
|`S_OK`|<span data-ttu-id="8a014-124">Erfolg.</span><span class="sxs-lookup"><span data-stu-id="8a014-124">Success.</span></span>|  
|`CORDBG_E_INVALID_OPCODE`|<span data-ttu-id="8a014-125">Die angegebene IL-Offsetsite ist keine Aufrufanweisung, oder die Funktion gibt `void` zurück.</span><span class="sxs-lookup"><span data-stu-id="8a014-125">The given IL offset site is not a call instruction, or the function returns `void`.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="8a014-126">Der angegebene IL-Offset ist ein richtiger Aufruf, der Rückgabetyp wird für das Abrufen eines Rückgabewerts nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8a014-126">The given IL offset is a proper call, but the return type is unsupported for getting a return value.</span></span>|  
  
 <span data-ttu-id="8a014-127">Die `ICorDebugCode3::GetReturnValueLiveOffset`-Methode ist nur auf x86- und AMD64-basierten Systemen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8a014-127">The `ICorDebugCode3::GetReturnValueLiveOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a014-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8a014-128">Requirements</span></span>  
 <span data-ttu-id="8a014-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a014-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a014-130">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a014-130">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a014-131">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a014-131">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a014-132">**.NET Framework Versionen:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a014-132">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a014-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8a014-133">See also</span></span>

- [<span data-ttu-id="8a014-134">GetReturnValueForILOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="8a014-134">GetReturnValueForILOffset Method</span></span>](icordebugilframe3-getreturnvalueforiloffset-method.md)
- [<span data-ttu-id="8a014-135">ICorDebugCode3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8a014-135">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
