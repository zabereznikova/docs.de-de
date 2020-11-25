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
ms.openlocfilehash: c135c051637858682c22db58d562e1d50eea562b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723700"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a><span data-ttu-id="f8d7e-102">ICLRDataTarget::SetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="f8d7e-102">ICLRDataTarget::SetThreadContext Method</span></span>

<span data-ttu-id="f8d7e-103">Legt den aktuellen Kontext des angegebenen Threads im Ziel Prozess fest.</span><span class="sxs-lookup"><span data-stu-id="f8d7e-103">Sets the current context of the specified thread in the target process.</span></span> <span data-ttu-id="f8d7e-104">Diese Methode wird vom Common Language Runtime (CLR)-Datenzugriffs Dienst aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="f8d7e-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8d7e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8d7e-105">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8d7e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f8d7e-106">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="f8d7e-107">in Der Betriebssystem Bezeichner eines Threads im Ziel Prozess.</span><span class="sxs-lookup"><span data-stu-id="f8d7e-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="f8d7e-108">in Die Größe des Kontexts.</span><span class="sxs-lookup"><span data-stu-id="f8d7e-108">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="f8d7e-109">in Zeiger auf einen Puffer, der den Kontext enthält.</span><span class="sxs-lookup"><span data-stu-id="f8d7e-109">[in] Pointer to a buffer containing the context.</span></span>  
  
 <span data-ttu-id="f8d7e-110">Die Daten im `context` Puffer werden im Format der Win32- `CONTEXT` Struktur angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f8d7e-110">The data in the `context` buffer will be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="f8d7e-111">Der Kontext gibt prozessorspezifische Register Daten an, sodass die Definition der Win32 `CONTEXT` -Struktur von der Architektur des Prozessors abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="f8d7e-111">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="f8d7e-112">Die Definition der Win32-Struktur finden Sie in der Header Datei "Winnt. h" `CONTEXT` .</span><span class="sxs-lookup"><span data-stu-id="f8d7e-112">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8d7e-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f8d7e-113">Remarks</span></span>  

 <span data-ttu-id="f8d7e-114">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="f8d7e-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8d7e-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f8d7e-115">Requirements</span></span>  

 <span data-ttu-id="f8d7e-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8d7e-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8d7e-117">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="f8d7e-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="f8d7e-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8d7e-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8d7e-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8d7e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8d7e-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f8d7e-120">See also</span></span>

- [<span data-ttu-id="f8d7e-121">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8d7e-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
