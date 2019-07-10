---
title: _EFN_StackTrace-Funktion
ms.date: 03/30/2017
api_name:
- _EFN_StackTrace
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_StackTrace
helpviewer_keywords:
- _EFN_StackTrace function [.NET Framework debugging]
ms.assetid: caea7754-867c-4360-a65c-5ced4408fd9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 687fdd0735e6cb0f3a727c8a2da3cf33bffb6a39
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738980"
---
# <a name="efnstacktrace-function"></a><span data-ttu-id="b369d-102">\_EFN\_StackTrace-Funktion</span><span class="sxs-lookup"><span data-stu-id="b369d-102">\_EFN\_StackTrace Function</span></span>
<span data-ttu-id="b369d-103">Stellt eine Textdarstellung einer verwalteten Stapelüberwachung und ein Array von `CONTEXT`-Datensätzen bereit, einen Datensatz für jeden Übergang zwischen nicht verwaltetem und verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="b369d-103">Provides a text representation of a managed stack trace and an array of `CONTEXT` records, one for each transition between unmanaged and managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b369d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b369d-104">Syntax</span></span>  
  
```cpp  
HRESULT CALLBACK _EFN_StackTrace(  
    [in]  PDEBUG_CLIENT  Client,  
    [out] WCHAR          wszTextOut[],  
    [out] size_t         *puiTextLength,  
    [out] LPVOID         pTransitionContexts,  
    [out] size_t         *puiTransitionContextCount,  
    [in]  size_t         uiSizeOfContext,  
    [in]  DWORD          Flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b369d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b369d-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="b369d-106">[in] Der Client, der gedebuggt wird.</span><span class="sxs-lookup"><span data-stu-id="b369d-106">[in] The client being debugged.</span></span>  
  
 `wszTextOut`  
 <span data-ttu-id="b369d-107">[out] Der Text-Darstellung der stapelüberwachung.</span><span class="sxs-lookup"><span data-stu-id="b369d-107">[out] The text representation of the stack trace.</span></span>  
  
 `puiTextLength`  
 <span data-ttu-id="b369d-108">[out] Ein Zeiger auf die Anzahl der Zeichen in `wszTextOut`.</span><span class="sxs-lookup"><span data-stu-id="b369d-108">[out] A pointer to the number of characters in `wszTextOut`.</span></span>  
  
 `pTransitionContexts`  
 <span data-ttu-id="b369d-109">[out] Das Array von Übergang Kontexte.</span><span class="sxs-lookup"><span data-stu-id="b369d-109">[out] The array of transition contexts.</span></span>  
  
 `puiTransitionContextCount`  
 <span data-ttu-id="b369d-110">[out] Ein Zeiger auf die Anzahl der von Übergangskontexten im Array.</span><span class="sxs-lookup"><span data-stu-id="b369d-110">[out] A pointer to the number of transition contexts in the array.</span></span>  
  
 `uiSizeOfContext`  
 <span data-ttu-id="b369d-111">[in] Die Größe der Context-Struktur.</span><span class="sxs-lookup"><span data-stu-id="b369d-111">[in] The size of the context structure.</span></span>  
  
 `Flags`  
 <span data-ttu-id="b369d-112">[in] Auf 0 oder SOS_STACKTRACE_SHOWADDRESSES (0 x 01) festgelegt, um die EBP-Register und die EINGABETASTE Stack Pointer (ESP) vor jeder `module!functionname` Zeile.</span><span class="sxs-lookup"><span data-stu-id="b369d-112">[in] Set to either 0 or SOS_STACKTRACE_SHOWADDRESSES (0x01) to show the EBP register and the enter stack pointer (ESP) in front of each `module!functionname` line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b369d-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b369d-113">Remarks</span></span>  
 <span data-ttu-id="b369d-114">Die `_EFN_StackTrace` Struktur kann von einer programmgesteuerten Schnittstelle von WinDbg aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b369d-114">The `_EFN_StackTrace` structure can be called from a WinDbg programmatic interface.</span></span> <span data-ttu-id="b369d-115">Parameter werden wie folgt verwendet:</span><span class="sxs-lookup"><span data-stu-id="b369d-115">Parameters are used as follows:</span></span>  
  
- <span data-ttu-id="b369d-116">Wenn `wszTextOut` ist null und `puiTextLength` ist nicht null ist, die Funktion gibt die Länge der Zeichenfolge in `puiTextLength`.</span><span class="sxs-lookup"><span data-stu-id="b369d-116">If `wszTextOut` is null and `puiTextLength` is not null, the function returns the string length in `puiTextLength`.</span></span>  
  
- <span data-ttu-id="b369d-117">Wenn `wszTextOut` ist nicht null ist, speichert die Funktion Text in `wszTextOut` bis zu dessen Speicherort vom `puiTextLength`.</span><span class="sxs-lookup"><span data-stu-id="b369d-117">If `wszTextOut` is not null, the function stores text in `wszTextOut` up to the location indicated by `puiTextLength`.</span></span> <span data-ttu-id="b369d-118">Es zurückgegeben war es genügend Platz im Puffer oder E_OUTOFMEMORY zurückgegeben, wenn der Puffer nicht groß genug war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="b369d-118">It returns successfully if there was enough room in the buffer, or returns E_OUTOFMEMORY if the buffer was not long enough.</span></span>  
  
- <span data-ttu-id="b369d-119">Der Übergangsteil der Funktion wird ignoriert, wenn `pTransitionContexts` und `puiTransitionContextCount` beide null sind.</span><span class="sxs-lookup"><span data-stu-id="b369d-119">The transition portion of the function is ignored if `pTransitionContexts` and `puiTransitionContextCount` are both null.</span></span> <span data-ttu-id="b369d-120">In diesem Fall stellt die Funktion Aufrufern nur die Funktionsnamen Textausgabe.</span><span class="sxs-lookup"><span data-stu-id="b369d-120">In this case, the function provides callers with text output of only the function names.</span></span>  
  
- <span data-ttu-id="b369d-121">Wenn `pTransitionContexts` ist null und `puiTransitionContextCount` ist nicht null ist, gibt die Funktion die erforderliche Anzahl von Kontext-Einträge im `puiTransitionContextCount`.</span><span class="sxs-lookup"><span data-stu-id="b369d-121">If `pTransitionContexts` is null and `puiTransitionContextCount` is not null, the function returns the necessary number of context entries in `puiTransitionContextCount`.</span></span>  
  
- <span data-ttu-id="b369d-122">Wenn `pTransitionContexts` ist nicht null ist, die Funktion behandelt es als ein Array von Strukturen der Länge `puiTransitionContextCount`.</span><span class="sxs-lookup"><span data-stu-id="b369d-122">If `pTransitionContexts` is not null, the function treats it as an array of structures of length `puiTransitionContextCount`.</span></span> <span data-ttu-id="b369d-123">Die Größe der Struktur erhält von `uiSizeOfContext`, muss die Größe des [SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) oder `CONTEXT` für die Architektur.</span><span class="sxs-lookup"><span data-stu-id="b369d-123">The structure size is given by `uiSizeOfContext`, and must be the size of [SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) or `CONTEXT` for the architecture.</span></span>  
  
- <span data-ttu-id="b369d-124">`wszTextOut` Im folgenden Format geschrieben:</span><span class="sxs-lookup"><span data-stu-id="b369d-124">`wszTextOut` is written in the following format:</span></span>  
  
    ```  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
- <span data-ttu-id="b369d-125">Wenn der Offset in hexadezimal 0 x 0 ist, wird kein Offset geschrieben.</span><span class="sxs-lookup"><span data-stu-id="b369d-125">If the offset in hex is 0x0, no offset is written.</span></span>  
  
- <span data-ttu-id="b369d-126">Es ist kein verwalteter Code für den Thread aktuell im Kontext, gibt die Funktion SOS_E_NOMANAGEDCODE zurück.</span><span class="sxs-lookup"><span data-stu-id="b369d-126">If there is no managed code on the thread currently in context, the function returns SOS_E_NOMANAGEDCODE.</span></span>  
  
- <span data-ttu-id="b369d-127">Die `Flags` Parameter ist entweder 0 oder SOS_STACKTRACE_SHOWADDRESSES um EBP und ESP vor jeder `module!functionname` Zeile.</span><span class="sxs-lookup"><span data-stu-id="b369d-127">The `Flags` parameter is either 0 or SOS_STACKTRACE_SHOWADDRESSES to see EBP and ESP in front of each `module!functionname` line.</span></span> <span data-ttu-id="b369d-128">Standardmäßig ist es 0.</span><span class="sxs-lookup"><span data-stu-id="b369d-128">By default, it is 0.</span></span>  
  
    ```  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a><span data-ttu-id="b369d-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b369d-129">Requirements</span></span>  
 <span data-ttu-id="b369d-130">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b369d-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b369d-131">**Header:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="b369d-131">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="b369d-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b369d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b369d-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b369d-133">See also</span></span>

- [<span data-ttu-id="b369d-134">Debuggen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="b369d-134">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
