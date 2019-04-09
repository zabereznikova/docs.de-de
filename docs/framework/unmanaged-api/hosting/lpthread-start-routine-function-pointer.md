---
title: LPTHREAD_START_ROUTINE-Funktionszeiger
ms.date: 03/30/2017
api_name:
- LPTHREAD_START_ROUTINE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- LPTHREAD_START_ROUTINE
helpviewer_keywords:
- LPTHREAD_START_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 7b9b93b0-fe92-42ba-8693-701168a29dde
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 27d1837f9f9f11ad34140f50ec41aa6fe8a62160
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119313"
---
# <a name="lpthreadstartroutine-function-pointer"></a><span data-ttu-id="f2b53-102">LPTHREAD_START_ROUTINE-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="f2b53-102">LPTHREAD_START_ROUTINE Function Pointer</span></span>
<span data-ttu-id="f2b53-103">Zeigt auf eine Funktion, die den Host benachrichtigt, dass eine Threadausführung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="f2b53-103">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 <span data-ttu-id="f2b53-104">Dieser Funktionszeiger ist veraltet, der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2b53-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2b53-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f2b53-105">Syntax</span></span>  
  
```  
typedef DWORD (__stdcall *LPTHREAD_START_ROUTINE) (  
    [in] LPVOID lpThreadParameter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2b53-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f2b53-106">Parameters</span></span>  
 `lpThreadParameter`  
 <span data-ttu-id="f2b53-107">[in] Ein Zeiger auf den Code, der Ausführung gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="f2b53-107">[in] A pointer to the code that has started executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2b53-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f2b53-108">Remarks</span></span>  
 <span data-ttu-id="f2b53-109">Die Funktion, die die `LPTHREAD_START_ROUTINE` ist eine Callback-Funktion und muss vom Writer der hostanwendung implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="f2b53-109">The function to which `LPTHREAD_START_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2b53-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f2b53-110">Requirements</span></span>  
 <span data-ttu-id="f2b53-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2b53-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2b53-112">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f2b53-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f2b53-113">**Bibliothek:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="f2b53-113">**Library:** MSCorWks.dll</span></span>  
  
 **<span data-ttu-id="f2b53-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="f2b53-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f2b53-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2b53-115">See also</span></span>

- [<span data-ttu-id="f2b53-116">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="f2b53-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
