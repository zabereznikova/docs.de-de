---
title: WAITORTIMERCALLBACK-Funktionszeiger
ms.date: 03/30/2017
api_name:
- WAITORTIMERCALLBACK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAITORTIMERCALLBACK
helpviewer_keywords:
- WAITORTIMERCALLBACK function pointer [.NET Framework hosting]
ms.assetid: 1fec4aef-0a06-4df0-bae7-d31a9ef9603d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f938c7dcf08654eef1e2403426eb5c54d6d2a6b3
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490123"
---
# <a name="waitortimercallback-function-pointer"></a><span data-ttu-id="f6cf1-102">WAITORTIMERCALLBACK-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="f6cf1-102">WAITORTIMERCALLBACK Function Pointer</span></span>
<span data-ttu-id="f6cf1-103">Verweist auf eine Funktion, die benachrichtigt den Host, die ein Wait-handle (<xref:System.Threading.WaitHandle>) hat signalisiert wurde oder das Timeout.</span><span class="sxs-lookup"><span data-stu-id="f6cf1-103">Points to a function that notifies the host that a wait handle (<xref:System.Threading.WaitHandle>) has either been signaled or timed out.</span></span>  
  
 <span data-ttu-id="f6cf1-104">Dieser Funktionszeiger wurde in .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="f6cf1-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6cf1-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f6cf1-105">Syntax</span></span>  
  
```  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6cf1-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f6cf1-106">Parameters</span></span>  
 `lpParameter`  
 <span data-ttu-id="f6cf1-107">[in] Ein Zeiger auf ein Objekt, das vom Host definierten Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="f6cf1-107">[in] A pointer to an object that contains information defined by the host.</span></span>  
  
 `TimerOrWaitFired`  
 <span data-ttu-id="f6cf1-108">[in] `true` Wenn Wait-Handles, die ein Timeout oder `false` , wenn ein Signal gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="f6cf1-108">[in] `true` if the wait handle timed out, or `false` if it was signaled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6cf1-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f6cf1-109">Remarks</span></span>  
 <span data-ttu-id="f6cf1-110">Die Funktion, die die `WAITORTIMERCALLBACK` ist eine Callback-Funktion und muss vom Writer der hostanwendung implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="f6cf1-110">The function to which `WAITORTIMERCALLBACK` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6cf1-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f6cf1-111">Requirements</span></span>  
 <span data-ttu-id="f6cf1-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6cf1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6cf1-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f6cf1-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f6cf1-114">**Bibliothek:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="f6cf1-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="f6cf1-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6cf1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6cf1-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6cf1-116">See also</span></span>

- [<span data-ttu-id="f6cf1-117">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="f6cf1-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
