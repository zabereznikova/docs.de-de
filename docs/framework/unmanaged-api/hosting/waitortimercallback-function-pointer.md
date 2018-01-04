---
title: WAITORTIMERCALLBACK-Funktionszeiger
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: WAITORTIMERCALLBACK
api_location: mscoree.dll
api_type: COM
f1_keywords: WAITORTIMERCALLBACK
helpviewer_keywords: WAITORTIMERCALLBACK function pointer [.NET Framework hosting]
ms.assetid: 1fec4aef-0a06-4df0-bae7-d31a9ef9603d
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f39c023c6911ca0bcc6b62a562785c069d846d15
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="waitortimercallback-function-pointer"></a><span data-ttu-id="11197-102">WAITORTIMERCALLBACK-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="11197-102">WAITORTIMERCALLBACK Function Pointer</span></span>
<span data-ttu-id="11197-103">Zeigt auf eine Funktion, die benachrichtigt den Host, die ein Wait-handle (<xref:System.Threading.WaitHandle>) hat signalisiert wurde oder das Timeout.</span><span class="sxs-lookup"><span data-stu-id="11197-103">Points to a function that notifies the host that a wait handle (<xref:System.Threading.WaitHandle>) has either been signaled or timed out.</span></span>  
  
 <span data-ttu-id="11197-104">Diese Funktionszeiger ist veraltet die [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11197-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11197-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="11197-105">Syntax</span></span>  
  
```  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="11197-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="11197-106">Parameters</span></span>  
 `lpParameter`  
 <span data-ttu-id="11197-107">[in] Ein Zeiger auf ein Objekt, das vom Host definierten Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="11197-107">[in] A pointer to an object that contains information defined by the host.</span></span>  
  
 `TimerOrWaitFired`  
 <span data-ttu-id="11197-108">[in] `true` , wenn das Wait-Handle, das ein Timeout oder `false` Wenn es signalisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="11197-108">[in] `true` if the wait handle timed out, or `false` if it was signaled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11197-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="11197-109">Remarks</span></span>  
 <span data-ttu-id="11197-110">Die Funktion, die die `WAITORTIMERCALLBACK` Punkt ist eine Rückruffunktion und muss vom Writer der Hostinganwendung implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="11197-110">The function to which `WAITORTIMERCALLBACK` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11197-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="11197-111">Requirements</span></span>  
 <span data-ttu-id="11197-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11197-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11197-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="11197-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="11197-114">**Bibliothek:** "Mscorwks.dll"</span><span class="sxs-lookup"><span data-stu-id="11197-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="11197-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11197-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11197-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11197-116">See Also</span></span>  
 [<span data-ttu-id="11197-117">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="11197-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
