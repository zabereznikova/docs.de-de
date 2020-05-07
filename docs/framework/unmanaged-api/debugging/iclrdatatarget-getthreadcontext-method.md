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
ms.openlocfilehash: 5c0fb023dd355f3a9c1ed846913f86b354592ed5
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860605"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a><span data-ttu-id="57bad-102">ICLRDataTarget::GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="57bad-102">ICLRDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="57bad-103">Ruft den aktuellen Ausführungs Kontext für den angegebenen Thread im Ziel Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="57bad-103">Gets the current execution context for the given thread in the target process.</span></span> <span data-ttu-id="57bad-104">Diese Methode wird vom Common Language Runtime Data Access Services aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="57bad-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57bad-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="57bad-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]
        BYTE                *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57bad-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="57bad-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="57bad-107">in Der Betriebssystem Bezeichner eines Threads im Ziel Prozess.</span><span class="sxs-lookup"><span data-stu-id="57bad-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="57bad-108">in Flags, die angeben, welche Teile des Kontexts zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="57bad-108">[in] Flags that specify which parts of the context to return.</span></span> <span data-ttu-id="57bad-109">Die-Implementierung gibt mindestens diese Teile des Kontexts zurück.</span><span class="sxs-lookup"><span data-stu-id="57bad-109">The implementation will return at least these parts of the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="57bad-110">in Die Größe des Kontexts.</span><span class="sxs-lookup"><span data-stu-id="57bad-110">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="57bad-111">vorgenommen Zeiger auf einen Puffer, in den der Kontext platziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="57bad-111">[out] Pointer to a buffer in which to place the context.</span></span>  
  
 <span data-ttu-id="57bad-112">Die Daten im `context` Puffer müssen das Format der Win32 `CONTEXT` -Struktur aufweisen.</span><span class="sxs-lookup"><span data-stu-id="57bad-112">The data in the `context` buffer must be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="57bad-113">Der Kontext gibt prozessorspezifische Register Daten an, sodass die Definition der Win32 `CONTEXT` -Struktur von der Architektur des Prozessors abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="57bad-113">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="57bad-114">Die Definition der Win32 `CONTEXT` -Struktur finden Sie in der Header Datei "Winnt. h".</span><span class="sxs-lookup"><span data-stu-id="57bad-114">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57bad-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="57bad-115">Remarks</span></span>  
 <span data-ttu-id="57bad-116">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="57bad-116">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57bad-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="57bad-117">Requirements</span></span>  
 <span data-ttu-id="57bad-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57bad-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57bad-119">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="57bad-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="57bad-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57bad-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57bad-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57bad-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57bad-122">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="57bad-122">See also</span></span>

- [<span data-ttu-id="57bad-123">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57bad-123">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
