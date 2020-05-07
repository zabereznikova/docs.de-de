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
ms.openlocfilehash: a725aa2c0f1fdea523bbf7cba880bc805f855782
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860737"
---
# <a name="_efn_stacktrace-function"></a><span data-ttu-id="2d294-102">\_EFN\_StackTrace-Funktion</span><span class="sxs-lookup"><span data-stu-id="2d294-102">\_EFN\_StackTrace Function</span></span>
<span data-ttu-id="2d294-103">Stellt eine Textdarstellung einer verwalteten Stapelüberwachung und ein Array von `CONTEXT`-Datensätzen bereit, einen Datensatz für jeden Übergang zwischen nicht verwaltetem und verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="2d294-103">Provides a text representation of a managed stack trace and an array of `CONTEXT` records, one for each transition between unmanaged and managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d294-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d294-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="2d294-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2d294-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="2d294-106">in Der Client, der deentschlgt wird.</span><span class="sxs-lookup"><span data-stu-id="2d294-106">[in] The client being debugged.</span></span>  
  
 `wszTextOut`  
 <span data-ttu-id="2d294-107">vorgenommen Die Textdarstellung der Stapel Überwachung.</span><span class="sxs-lookup"><span data-stu-id="2d294-107">[out] The text representation of the stack trace.</span></span>  
  
 `puiTextLength`  
 <span data-ttu-id="2d294-108">vorgenommen Ein Zeiger auf die Anzahl von Zeichen in `wszTextOut`.</span><span class="sxs-lookup"><span data-stu-id="2d294-108">[out] A pointer to the number of characters in `wszTextOut`.</span></span>  
  
 `pTransitionContexts`  
 <span data-ttu-id="2d294-109">vorgenommen Das Array von Übergangs Kontexten.</span><span class="sxs-lookup"><span data-stu-id="2d294-109">[out] The array of transition contexts.</span></span>  
  
 `puiTransitionContextCount`  
 <span data-ttu-id="2d294-110">vorgenommen Ein Zeiger auf die Anzahl der Übergangs Kontexte im Array.</span><span class="sxs-lookup"><span data-stu-id="2d294-110">[out] A pointer to the number of transition contexts in the array.</span></span>  
  
 `uiSizeOfContext`  
 <span data-ttu-id="2d294-111">in Die Größe der Kontext Struktur.</span><span class="sxs-lookup"><span data-stu-id="2d294-111">[in] The size of the context structure.</span></span>  
  
 `Flags`  
 <span data-ttu-id="2d294-112">in Legen Sie entweder auf 0 oder SOS_STACKTRACE_SHOWADDRESSES (0x01) fest, um das EBP-Register und den Eingabe Stapelzeiger (ESP) vor `module!functionname` jeder Zeile anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2d294-112">[in] Set to either 0 or SOS_STACKTRACE_SHOWADDRESSES (0x01) to show the EBP register and the enter stack pointer (ESP) in front of each `module!functionname` line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d294-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2d294-113">Remarks</span></span>  
 <span data-ttu-id="2d294-114">Die `_EFN_StackTrace` Struktur kann von einer WinDbg-programmgesteuerten Schnittstelle aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2d294-114">The `_EFN_StackTrace` structure can be called from a WinDbg programmatic interface.</span></span> <span data-ttu-id="2d294-115">Parameter werden wie folgt verwendet:</span><span class="sxs-lookup"><span data-stu-id="2d294-115">Parameters are used as follows:</span></span>  
  
- <span data-ttu-id="2d294-116">Wenn `wszTextOut` NULL ist und `puiTextLength` nicht NULL ist, gibt die Funktion die Zeichen folgen Länge `puiTextLength`in zurück.</span><span class="sxs-lookup"><span data-stu-id="2d294-116">If `wszTextOut` is null and `puiTextLength` is not null, the function returns the string length in `puiTextLength`.</span></span>  
  
- <span data-ttu-id="2d294-117">Wenn `wszTextOut` nicht NULL ist, speichert die Funktion Text in `wszTextOut` bis zu dem Speicherort, `puiTextLength`der von angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2d294-117">If `wszTextOut` is not null, the function stores text in `wszTextOut` up to the location indicated by `puiTextLength`.</span></span> <span data-ttu-id="2d294-118">Es wird erfolgreich zurückgegeben, wenn genügend Platz im Puffer vorhanden ist, oder es wird E_OUTOFMEMORY zurückgegeben, wenn der Puffer nicht lang genug ist.</span><span class="sxs-lookup"><span data-stu-id="2d294-118">It returns successfully if there was enough room in the buffer, or returns E_OUTOFMEMORY if the buffer was not long enough.</span></span>  
  
- <span data-ttu-id="2d294-119">Der Übergangsteil der Funktion wird ignoriert, wenn `pTransitionContexts` und `puiTransitionContextCount` beide NULL sind.</span><span class="sxs-lookup"><span data-stu-id="2d294-119">The transition portion of the function is ignored if `pTransitionContexts` and `puiTransitionContextCount` are both null.</span></span> <span data-ttu-id="2d294-120">In diesem Fall stellt die-Funktion Aufrufern nur die Textausgabe der Funktionsnamen bereit.</span><span class="sxs-lookup"><span data-stu-id="2d294-120">In this case, the function provides callers with text output of only the function names.</span></span>  
  
- <span data-ttu-id="2d294-121">Wenn `pTransitionContexts` NULL ist und `puiTransitionContextCount` nicht NULL ist, gibt die-Funktion die erforderliche Anzahl von Kontext Einträgen `puiTransitionContextCount`in zurück.</span><span class="sxs-lookup"><span data-stu-id="2d294-121">If `pTransitionContexts` is null and `puiTransitionContextCount` is not null, the function returns the necessary number of context entries in `puiTransitionContextCount`.</span></span>  
  
- <span data-ttu-id="2d294-122">Wenn `pTransitionContexts` nicht NULL ist, behandelt die Funktion Sie als Array von Längen `puiTransitionContextCount`-Strukturen.</span><span class="sxs-lookup"><span data-stu-id="2d294-122">If `pTransitionContexts` is not null, the function treats it as an array of structures of length `puiTransitionContextCount`.</span></span> <span data-ttu-id="2d294-123">Die Struktur Größe wird von `uiSizeOfContext`angegeben, und es muss sich um die Größe von [SimpleContext](stacktrace-simplecontext-structure.md) oder `CONTEXT` für die-Architektur handeln.</span><span class="sxs-lookup"><span data-stu-id="2d294-123">The structure size is given by `uiSizeOfContext`, and must be the size of [SimpleContext](stacktrace-simplecontext-structure.md) or `CONTEXT` for the architecture.</span></span>  
  
- <span data-ttu-id="2d294-124">`wszTextOut`wird im folgenden Format geschrieben:</span><span class="sxs-lookup"><span data-stu-id="2d294-124">`wszTextOut` is written in the following format:</span></span>  
  
    ```output  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
- <span data-ttu-id="2d294-125">Wenn der Offset in Hex 0x0 ist, wird kein Offset geschrieben.</span><span class="sxs-lookup"><span data-stu-id="2d294-125">If the offset in hex is 0x0, no offset is written.</span></span>  
  
- <span data-ttu-id="2d294-126">Wenn im Thread derzeit kein verwalteter Code vorhanden ist, gibt die Funktion SOS_E_NOMANAGEDCODE zurück.</span><span class="sxs-lookup"><span data-stu-id="2d294-126">If there is no managed code on the thread currently in context, the function returns SOS_E_NOMANAGEDCODE.</span></span>  
  
- <span data-ttu-id="2d294-127">Der `Flags` -Parameter ist entweder 0 oder SOS_STACKTRACE_SHOWADDRESSES, um EBP und ESP vor jeder `module!functionname` Zeile anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2d294-127">The `Flags` parameter is either 0 or SOS_STACKTRACE_SHOWADDRESSES to see EBP and ESP in front of each `module!functionname` line.</span></span> <span data-ttu-id="2d294-128">Standardmäßig ist der Wert 0.</span><span class="sxs-lookup"><span data-stu-id="2d294-128">By default, it is 0.</span></span>  
  
    ```cpp  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a><span data-ttu-id="2d294-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2d294-129">Requirements</span></span>  
 <span data-ttu-id="2d294-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d294-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d294-131">**Header:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="2d294-131">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="2d294-132">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d294-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d294-133">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="2d294-133">See also</span></span>

- [<span data-ttu-id="2d294-134">Debuggen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="2d294-134">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
