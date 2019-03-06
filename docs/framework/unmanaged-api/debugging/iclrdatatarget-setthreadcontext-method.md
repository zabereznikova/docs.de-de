---
title: ICLRDataTarget::SetThreadContext-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetThreadContext
helpviewer_keywords:
- SetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::SetThreadContext method [.NET Framework debugging]
ms.assetid: 103c8502-81fe-40d7-9c1e-9008d8fb19e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b4ab183bbe82c8e64b833c8fcdbc1e05ceb18e1f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482248"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a><span data-ttu-id="0cf0d-102">ICLRDataTarget::SetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="0cf0d-102">ICLRDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="0cf0d-103">Legt den aktuellen Kontext des angegebenen Threads im Zielprozess fest.</span><span class="sxs-lookup"><span data-stu-id="0cf0d-103">Sets the current context of the specified thread in the target process.</span></span> <span data-ttu-id="0cf0d-104">Diese Methode wird von den Datenzugriffsdiensten der common Language Runtime (CLR) aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="0cf0d-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cf0d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0cf0d-105">Syntax</span></span>  
  
```  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]   
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0cf0d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="0cf0d-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="0cf0d-107">[in] Der Betriebssystem-Bezeichner eines Threads im Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="0cf0d-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="0cf0d-108">[in] Die Größe des Kontexts.</span><span class="sxs-lookup"><span data-stu-id="0cf0d-108">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="0cf0d-109">[in] Zeiger auf einen Puffer, der den Kontext enthält.</span><span class="sxs-lookup"><span data-stu-id="0cf0d-109">[in] Pointer to a buffer containing the context.</span></span>  
  
 <span data-ttu-id="0cf0d-110">Die Daten in die `context` Puffer werden im Format von Win32 `CONTEXT` Struktur.</span><span class="sxs-lookup"><span data-stu-id="0cf0d-110">The data in the `context` buffer will be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="0cf0d-111">Den Kontext angibt, macht prozessorspezifische Registerdaten, also die Definition von Win32 `CONTEXT` Struktur hängt von der Prozessorarchitektur.</span><span class="sxs-lookup"><span data-stu-id="0cf0d-111">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="0cf0d-112">Finden Sie in der Headerdatei "WinNT.h" für die Definition von Win32 `CONTEXT` Struktur.</span><span class="sxs-lookup"><span data-stu-id="0cf0d-112">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0cf0d-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0cf0d-113">Remarks</span></span>  
 <span data-ttu-id="0cf0d-114">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="0cf0d-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cf0d-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0cf0d-115">Requirements</span></span>  
 <span data-ttu-id="0cf0d-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cf0d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cf0d-117">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="0cf0d-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="0cf0d-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0cf0d-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0cf0d-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cf0d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cf0d-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0cf0d-120">See also</span></span>
- [<span data-ttu-id="0cf0d-121">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0cf0d-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
