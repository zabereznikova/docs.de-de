---
title: LPTHREAD_START_ROUTINE-Funktionszeiger
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LPTHREAD_START_ROUTINE
api_location: mscoree.dll
api_type: COM
f1_keywords: LPTHREAD_START_ROUTINE
helpviewer_keywords: LPTHREAD_START_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 7b9b93b0-fe92-42ba-8693-701168a29dde
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f29e4e52f9629073d676903e3f828a84023065bd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="lpthreadstartroutine-function-pointer"></a><span data-ttu-id="1a4dd-102">LPTHREAD_START_ROUTINE-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="1a4dd-102">LPTHREAD_START_ROUTINE Function Pointer</span></span>
<span data-ttu-id="1a4dd-103">Zeigt auf eine Funktion, die den Host benachrichtigt, dass eine Threadausführung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="1a4dd-103">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 <span data-ttu-id="1a4dd-104">Diese Funktionszeiger ist veraltet die [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1a4dd-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a4dd-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1a4dd-105">Syntax</span></span>  
  
```  
typedef DWORD (__stdcall *LPTHREAD_START_ROUTINE) (  
    [in] LPVOID lpThreadParameter  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1a4dd-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="1a4dd-106">Parameters</span></span>  
 `lpThreadParameter`  
 <span data-ttu-id="1a4dd-107">[in] Ein Zeiger auf den Code, der Ausführung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="1a4dd-107">[in] A pointer to the code that has started executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a4dd-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1a4dd-108">Remarks</span></span>  
 <span data-ttu-id="1a4dd-109">Die Funktion, die die `LPTHREAD_START_ROUTINE` Punkt ist eine Rückruffunktion und muss vom Writer der Hostinganwendung implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="1a4dd-109">The function to which `LPTHREAD_START_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a4dd-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1a4dd-110">Requirements</span></span>  
 <span data-ttu-id="1a4dd-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a4dd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a4dd-112">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1a4dd-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1a4dd-113">**Bibliothek:** "Mscorwks.dll"</span><span class="sxs-lookup"><span data-stu-id="1a4dd-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="1a4dd-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a4dd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a4dd-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a4dd-115">See Also</span></span>  
 [<span data-ttu-id="1a4dd-116">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="1a4dd-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
