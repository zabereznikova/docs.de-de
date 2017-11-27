---
title: _EFN_StackTrace-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _EFN_StackTrace
api_location: mscordbi.dll
api_type: COM
f1_keywords: _EFN_StackTrace
helpviewer_keywords: _EFN_StackTrace function [.NET Framework debugging]
ms.assetid: caea7754-867c-4360-a65c-5ced4408fd9d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 031812b2c286c5647afb9c88882f22e2c7c3addf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="efnstacktrace-function"></a><span data-ttu-id="91215-102">_EFN_StackTrace-Funktion</span><span class="sxs-lookup"><span data-stu-id="91215-102">_EFN_StackTrace Function</span></span>
<span data-ttu-id="91215-103">Stellt eine Textdarstellung einer verwalteten Stapelüberwachung und ein Array von `CONTEXT`-Datensätzen bereit, einen Datensatz für jeden Übergang zwischen nicht verwaltetem und verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="91215-103">Provides a text representation of a managed stack trace and an array of `CONTEXT` records, one for each transition between unmanaged and managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91215-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="91215-104">Syntax</span></span>  
  
```  
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
  
#### <a name="parameters"></a><span data-ttu-id="91215-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="91215-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="91215-106">[in] Der Client, der debuggt wird.</span><span class="sxs-lookup"><span data-stu-id="91215-106">[in] The client being debugged.</span></span>  
  
 `wszTextOut`  
 <span data-ttu-id="91215-107">[out] Der Text-Darstellung der stapelüberwachung.</span><span class="sxs-lookup"><span data-stu-id="91215-107">[out] The text representation of the stack trace.</span></span>  
  
 `puiTextLength`  
 <span data-ttu-id="91215-108">[out] Ein Zeiger auf die Anzahl der Zeichen in `wszTextOut`.</span><span class="sxs-lookup"><span data-stu-id="91215-108">[out] A pointer to the number of characters in `wszTextOut`.</span></span>  
  
 `pTransitionContexts`  
 <span data-ttu-id="91215-109">[out] Das Array von Übergangskontexten.</span><span class="sxs-lookup"><span data-stu-id="91215-109">[out] The array of transition contexts.</span></span>  
  
 `puiTransitionContextCount`  
 <span data-ttu-id="91215-110">[out] Ein Zeiger auf die Anzahl von Übergangskontexten im Array.</span><span class="sxs-lookup"><span data-stu-id="91215-110">[out] A pointer to the number of transition contexts in the array.</span></span>  
  
 `uiSizeOfContext`  
 <span data-ttu-id="91215-111">[in] Die Größe der Context-Struktur.</span><span class="sxs-lookup"><span data-stu-id="91215-111">[in] The size of the context structure.</span></span>  
  
 `Flags`  
 <span data-ttu-id="91215-112">[in] Festgelegt auf 0 oder SOS_STACKTRACE_SHOWADDRESSES (0 x 01) anzuzeigende EBP-Register und die EINGABETASTE Stack-Pointer (ESP) vor jeder `module!functionname` Zeile.</span><span class="sxs-lookup"><span data-stu-id="91215-112">[in] Set to either 0 or SOS_STACKTRACE_SHOWADDRESSES (0x01) to show the EBP register and the enter stack pointer (ESP) in front of each `module!functionname` line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91215-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="91215-113">Remarks</span></span>  
 <span data-ttu-id="91215-114">Die `_EFN_StackTrace` Struktur kann von einem programmgesteuerten WinDbg-Schnittstelle aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="91215-114">The `_EFN_StackTrace` structure can be called from a WinDbg programmatic interface.</span></span> <span data-ttu-id="91215-115">Parameter werden wie folgt verwendet:</span><span class="sxs-lookup"><span data-stu-id="91215-115">Parameters are used as follows:</span></span>  
  
-   <span data-ttu-id="91215-116">Wenn `wszTextOut` ist null und `puiTextLength` ist ungleich null, die Funktion gibt die Länge der Zeichenfolge in `puiTextLength`.</span><span class="sxs-lookup"><span data-stu-id="91215-116">If `wszTextOut` is null and `puiTextLength` is not null, the function returns the string length in `puiTextLength`.</span></span>  
  
-   <span data-ttu-id="91215-117">Wenn `wszTextOut` ist nicht null ist, speichert die Funktion Text in `wszTextOut` bis zu dessen Speicherort vom `puiTextLength`.</span><span class="sxs-lookup"><span data-stu-id="91215-117">If `wszTextOut` is not null, the function stores text in `wszTextOut` up to the location indicated by `puiTextLength`.</span></span> <span data-ttu-id="91215-118">Es wurde erfolgreich ausgeführt, wenn ausreichend Platz im Puffer oder E_OUTOFMEMORY zurückgegeben wurde, wenn der Puffer nicht groß genug sind, wurde.</span><span class="sxs-lookup"><span data-stu-id="91215-118">It returns successfully if there was enough room in the buffer, or returns E_OUTOFMEMORY if the buffer was not long enough.</span></span>  
  
-   <span data-ttu-id="91215-119">Der Übergangsteil der Funktion wird ignoriert, wenn `pTransitionContexts` und `puiTransitionContextCount` sind beide null.</span><span class="sxs-lookup"><span data-stu-id="91215-119">The transition portion of the function is ignored if `pTransitionContexts` and `puiTransitionContextCount` are both null.</span></span> <span data-ttu-id="91215-120">In diesem Fall stellt die Funktion Aufrufern nur die Funktionsnamen Textausgabe.</span><span class="sxs-lookup"><span data-stu-id="91215-120">In this case, the function provides callers with text output of only the function names.</span></span>  
  
-   <span data-ttu-id="91215-121">Wenn `pTransitionContexts` ist null und `puiTransitionContextCount` ist ungleich null, die Funktion gibt die erforderliche Anzahl von Kontexteinträgen im `puiTransitionContextCount`.</span><span class="sxs-lookup"><span data-stu-id="91215-121">If `pTransitionContexts` is null and `puiTransitionContextCount` is not null, the function returns the necessary number of context entries in `puiTransitionContextCount`.</span></span>  
  
-   <span data-ttu-id="91215-122">Wenn `pTransitionContexts` ist nicht null ist, behandelt die Funktion sie als Array von Strukturen der Länge `puiTransitionContextCount`.</span><span class="sxs-lookup"><span data-stu-id="91215-122">If `pTransitionContexts` is not null, the function treats it as an array of structures of length `puiTransitionContextCount`.</span></span> <span data-ttu-id="91215-123">Die Größe der Struktur erhält vom `uiSizeOfContext`, muss die Größe des [SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) oder `CONTEXT` für die Architektur.</span><span class="sxs-lookup"><span data-stu-id="91215-123">The structure size is given by `uiSizeOfContext`, and must be the size of [SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) or `CONTEXT` for the architecture.</span></span>  
  
-   <span data-ttu-id="91215-124">`wszTextOut`Im folgenden Format geschrieben:</span><span class="sxs-lookup"><span data-stu-id="91215-124">`wszTextOut` is written in the following format:</span></span>  
  
    ```  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
-   <span data-ttu-id="91215-125">Wenn der Offset im Hexadezimalformat 0 x 0 ist, wird kein Offset geschrieben.</span><span class="sxs-lookup"><span data-stu-id="91215-125">If the offset in hex is 0x0, no offset is written.</span></span>  
  
-   <span data-ttu-id="91215-126">Es ist kein verwalteter Code auf dem Thread derzeit im Kontext, gibt die Funktion SOS_E_NOMANAGEDCODE zurück.</span><span class="sxs-lookup"><span data-stu-id="91215-126">If there is no managed code on the thread currently in context, the function returns SOS_E_NOMANAGEDCODE.</span></span>  
  
-   <span data-ttu-id="91215-127">Die `Flags` Parameter ist entweder 0 oder SOS_STACKTRACE_SHOWADDRESSES EBP und ESP vor jeder anzeigen `module!functionname` Zeile.</span><span class="sxs-lookup"><span data-stu-id="91215-127">The `Flags` parameter is either 0 or SOS_STACKTRACE_SHOWADDRESSES to see EBP and ESP in front of each `module!functionname` line.</span></span> <span data-ttu-id="91215-128">Standardmäßig ist es 0.</span><span class="sxs-lookup"><span data-stu-id="91215-128">By default, it is 0.</span></span>  
  
    ```  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a><span data-ttu-id="91215-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="91215-129">Requirements</span></span>  
 <span data-ttu-id="91215-130">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91215-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91215-131">**Header:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="91215-131">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="91215-132">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91215-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91215-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91215-133">See Also</span></span>  
 [<span data-ttu-id="91215-134">Debuggen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="91215-134">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
