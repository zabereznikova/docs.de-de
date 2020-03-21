---
title: ICLRDataTarget::GetThreadContext-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetThreadContext
helpviewer_keywords:
- ICLRDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: b9d8c3b5-3a2e-4225-95d4-dd052c4532c3
topic_type:
- apiref
ms.openlocfilehash: 3777ad4b12c7d0593c095c470aba81088137a859
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179179"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a><span data-ttu-id="e235e-102">ICLRDataTarget::GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="e235e-102">ICLRDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="e235e-103">Ruft den aktuellen Ausführungskontext für den angegebenen Thread im Zielprozess ab.</span><span class="sxs-lookup"><span data-stu-id="e235e-103">Gets the current execution context for the given thread in the target process.</span></span> <span data-ttu-id="e235e-104">Diese Methode wird von den Common Language Runtime-Datenzugriffsdiensten aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="e235e-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e235e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e235e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]
        BYTE                *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e235e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e235e-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="e235e-107">[in] Der Betriebssystembezeichner eines Threads im Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="e235e-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="e235e-108">[in] Flags, die angeben, welche Teile des Kontexts zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e235e-108">[in] Flags that specify which parts of the context to return.</span></span> <span data-ttu-id="e235e-109">Die Implementierung gibt zumindest diese Teile des Kontexts zurück.</span><span class="sxs-lookup"><span data-stu-id="e235e-109">The implementation will return at least these parts of the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="e235e-110">[in] Die Größe des Kontexts.</span><span class="sxs-lookup"><span data-stu-id="e235e-110">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="e235e-111">[out] Zeiger auf einen Puffer, in dem der Kontext platziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e235e-111">[out] Pointer to a buffer in which to place the context.</span></span>  
  
 <span data-ttu-id="e235e-112">Die Daten `context` im Puffer müssen im Format der `CONTEXT` Win32-Struktur vorliegen.</span><span class="sxs-lookup"><span data-stu-id="e235e-112">The data in the `context` buffer must be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="e235e-113">Der Kontext gibt prozessorspezifische Registerdaten an, sodass `CONTEXT` die Definition der Win32-Struktur von der Architektur des Prozessors abhängt.</span><span class="sxs-lookup"><span data-stu-id="e235e-113">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="e235e-114">Die Definition der Win32-Struktur `CONTEXT` finden Sie in der WinNT.h-Headerdatei.</span><span class="sxs-lookup"><span data-stu-id="e235e-114">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e235e-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e235e-115">Remarks</span></span>  
 <span data-ttu-id="e235e-116">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="e235e-116">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e235e-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e235e-117">Requirements</span></span>  
 <span data-ttu-id="e235e-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e235e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e235e-119">**Kopfzeile:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="e235e-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="e235e-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e235e-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e235e-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e235e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e235e-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e235e-122">See also</span></span>

- [<span data-ttu-id="e235e-123">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e235e-123">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
