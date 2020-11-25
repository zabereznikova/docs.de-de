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
ms.openlocfilehash: c86b65e136869603f93253678108b2ffa9d388e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730070"
---
# <a name="lpthread_start_routine-function-pointer"></a><span data-ttu-id="727fe-102">LPTHREAD_START_ROUTINE-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="727fe-102">LPTHREAD_START_ROUTINE Function Pointer</span></span>

<span data-ttu-id="727fe-103">Zeigt auf eine Funktion, die den Host benachrichtigt, dass eine Threadausführung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="727fe-103">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 <span data-ttu-id="727fe-104">Dieser Funktionszeiger wurde in der .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="727fe-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="727fe-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="727fe-105">Syntax</span></span>  
  
```cpp  
typedef DWORD (__stdcall *LPTHREAD_START_ROUTINE) (  
    [in] LPVOID lpThreadParameter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="727fe-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="727fe-106">Parameters</span></span>  

 `lpThreadParameter`  
 <span data-ttu-id="727fe-107">in Ein Zeiger auf den Code, der die Ausführung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="727fe-107">[in] A pointer to the code that has started executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="727fe-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="727fe-108">Remarks</span></span>  

 <span data-ttu-id="727fe-109">Die Funktion, auf die `LPTHREAD_START_ROUTINE` verweist, ist eine Rückruffunktion und muss vom Writer der Hostinganwendung implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="727fe-109">The function to which `LPTHREAD_START_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="727fe-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="727fe-110">Requirements</span></span>  

 <span data-ttu-id="727fe-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="727fe-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="727fe-112">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="727fe-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="727fe-113">**Bibliothek:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="727fe-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="727fe-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="727fe-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="727fe-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="727fe-115">See also</span></span>

- [<span data-ttu-id="727fe-116">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="727fe-116">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
