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
ms.openlocfilehash: 1d36ae3ef63c1324f77786ad55674bbdc257d984
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607133"
---
# <a name="waitortimercallback-function-pointer"></a><span data-ttu-id="a915d-102">WAITORTIMERCALLBACK-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="a915d-102">WAITORTIMERCALLBACK Function Pointer</span></span>
<span data-ttu-id="a915d-103">Verweist auf eine Funktion, die benachrichtigt den Host, die ein Wait-handle (<xref:System.Threading.WaitHandle>) hat signalisiert wurde oder das Timeout.</span><span class="sxs-lookup"><span data-stu-id="a915d-103">Points to a function that notifies the host that a wait handle (<xref:System.Threading.WaitHandle>) has either been signaled or timed out.</span></span>  
  
 <span data-ttu-id="a915d-104">Dieser Funktionszeiger ist veraltet, der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a915d-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a915d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a915d-105">Syntax</span></span>  
  
```  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a915d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="a915d-106">Parameters</span></span>  
 `lpParameter`  
 <span data-ttu-id="a915d-107">[in] Ein Zeiger auf ein Objekt, das vom Host definierten Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="a915d-107">[in] A pointer to an object that contains information defined by the host.</span></span>  
  
 `TimerOrWaitFired`  
 <span data-ttu-id="a915d-108">[in] `true` Wenn Wait-Handles, die ein Timeout oder `false` , wenn ein Signal gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="a915d-108">[in] `true` if the wait handle timed out, or `false` if it was signaled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a915d-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a915d-109">Remarks</span></span>  
 <span data-ttu-id="a915d-110">Die Funktion, die die `WAITORTIMERCALLBACK` ist eine Callback-Funktion und muss vom Writer der hostanwendung implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="a915d-110">The function to which `WAITORTIMERCALLBACK` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a915d-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a915d-111">Requirements</span></span>  
 <span data-ttu-id="a915d-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a915d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a915d-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a915d-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a915d-114">**Bibliothek:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="a915d-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="a915d-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a915d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a915d-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a915d-116">See also</span></span>
- [<span data-ttu-id="a915d-117">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="a915d-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
