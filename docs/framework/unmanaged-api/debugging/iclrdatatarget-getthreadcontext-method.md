---
title: ICLRDataTarget::GetThreadContext-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget.GetThreadContext
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget::GetThreadContext
helpviewer_keywords:
- ICLRDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: b9d8c3b5-3a2e-4225-95d4-dd052c4532c3
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 480b65b279dbc0359b078f3f1d543f63a0bfd0f6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdatatargetgetthreadcontext-method"></a><span data-ttu-id="97694-102">ICLRDataTarget::GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="97694-102">ICLRDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="97694-103">Ruft den aktuellen Ausführungskontext für den angegebenen Thread im Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="97694-103">Gets the current execution context for the given thread in the target process.</span></span> <span data-ttu-id="97694-104">Diese Methode wird von den Datenzugriffsdiensten der common Language Runtime aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="97694-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97694-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="97694-105">Syntax</span></span>  
  
```  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]   
        BYTE                *context  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="97694-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="97694-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="97694-107">[in] Der Betriebssystem-Bezeichner eines Threads im Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="97694-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="97694-108">[in] Flags, die angeben, welche Teile des Kontexts zurück.</span><span class="sxs-lookup"><span data-stu-id="97694-108">[in] Flags that specify which parts of the context to return.</span></span> <span data-ttu-id="97694-109">Die Implementierung gibt mindestens diese Teile des Kontexts zurück.</span><span class="sxs-lookup"><span data-stu-id="97694-109">The implementation will return at least these parts of the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="97694-110">[in] Die Größe des Kontexts.</span><span class="sxs-lookup"><span data-stu-id="97694-110">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="97694-111">[out] Ein Zeiger auf einen Puffer, in dem den Kontext platziert.</span><span class="sxs-lookup"><span data-stu-id="97694-111">[out] Pointer to a buffer in which to place the context.</span></span>  
  
 <span data-ttu-id="97694-112">Die Daten in der `context` Puffer muss im Format der Win32- `CONTEXT` Struktur.</span><span class="sxs-lookup"><span data-stu-id="97694-112">The data in the `context` buffer must be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="97694-113">Der Kontext gibt prozessorspezifische Registerdaten an, also die Definition der Win32- `CONTEXT` Struktur hängt von der Prozessorarchitektur.</span><span class="sxs-lookup"><span data-stu-id="97694-113">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="97694-114">Finden Sie in der Headerdatei "Winnt.h" für die Definition der Win32- `CONTEXT` Struktur.</span><span class="sxs-lookup"><span data-stu-id="97694-114">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97694-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="97694-115">Remarks</span></span>  
 <span data-ttu-id="97694-116">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="97694-116">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97694-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="97694-117">Requirements</span></span>  
 <span data-ttu-id="97694-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97694-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97694-119">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="97694-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="97694-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97694-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97694-121">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97694-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97694-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97694-122">See Also</span></span>  
 [<span data-ttu-id="97694-123">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="97694-123">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
