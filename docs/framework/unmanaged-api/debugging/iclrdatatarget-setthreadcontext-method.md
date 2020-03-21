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
ms.openlocfilehash: d76a907434b12b85aaedeef169390ec6f0df724a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179126"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a><span data-ttu-id="24443-102">ICLRDataTarget::SetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="24443-102">ICLRDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="24443-103">Legt den aktuellen Kontext des angegebenen Threads im Zielprozess fest.</span><span class="sxs-lookup"><span data-stu-id="24443-103">Sets the current context of the specified thread in the target process.</span></span> <span data-ttu-id="24443-104">Diese Methode wird von den ClR-Datenzugriffsdiensten (Common Language Runtime) aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="24443-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24443-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="24443-105">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24443-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="24443-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="24443-107">[in] Der Betriebssystembezeichner eines Threads im Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="24443-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="24443-108">[in] Die Größe des Kontexts.</span><span class="sxs-lookup"><span data-stu-id="24443-108">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="24443-109">[in] Zeiger auf einen Puffer, der den Kontext enthält.</span><span class="sxs-lookup"><span data-stu-id="24443-109">[in] Pointer to a buffer containing the context.</span></span>  
  
 <span data-ttu-id="24443-110">Die Daten `context` im Puffer werden im Format der `CONTEXT` Win32-Struktur vorliegen.</span><span class="sxs-lookup"><span data-stu-id="24443-110">The data in the `context` buffer will be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="24443-111">Der Kontext gibt prozessorspezifische Registerdaten an, sodass `CONTEXT` die Definition der Win32-Struktur von der Architektur des Prozessors abhängt.</span><span class="sxs-lookup"><span data-stu-id="24443-111">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="24443-112">Die Definition der Win32-Struktur `CONTEXT` finden Sie in der WinNT.h-Headerdatei.</span><span class="sxs-lookup"><span data-stu-id="24443-112">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24443-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="24443-113">Remarks</span></span>  
 <span data-ttu-id="24443-114">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="24443-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24443-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="24443-115">Requirements</span></span>  
 <span data-ttu-id="24443-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24443-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24443-117">**Kopfzeile:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="24443-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="24443-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24443-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24443-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24443-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24443-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="24443-120">See also</span></span>

- [<span data-ttu-id="24443-121">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24443-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
