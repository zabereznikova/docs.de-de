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
ms.openlocfilehash: c6e0c02af93b9df726202f397bbb2afc306f3b3a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73090882"
---
# <a name="lpthread_start_routine-function-pointer"></a><span data-ttu-id="530a8-102">LPTHREAD_START_ROUTINE-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="530a8-102">LPTHREAD_START_ROUTINE Function Pointer</span></span>
<span data-ttu-id="530a8-103">Zeigt auf eine Funktion, die den Host benachrichtigt, dass eine Threadausführung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="530a8-103">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 <span data-ttu-id="530a8-104">Dieser Funktionszeiger wurde in der .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="530a8-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="530a8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="530a8-105">Syntax</span></span>  
  
```cpp  
typedef DWORD (__stdcall *LPTHREAD_START_ROUTINE) (  
    [in] LPVOID lpThreadParameter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="530a8-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="530a8-106">Parameters</span></span>  
 `lpThreadParameter`  
 <span data-ttu-id="530a8-107">in Ein Zeiger auf den Code, der die Ausführung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="530a8-107">[in] A pointer to the code that has started executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="530a8-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="530a8-108">Remarks</span></span>  
 <span data-ttu-id="530a8-109">Die Funktion, zu der `LPTHREAD_START_ROUTINE` Punkte eine Rückruffunktion ist und vom Writer der Hostinganwendung implementiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="530a8-109">The function to which `LPTHREAD_START_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="530a8-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="530a8-110">Requirements</span></span>  
 <span data-ttu-id="530a8-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="530a8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="530a8-112">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="530a8-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="530a8-113">**Bibliothek:** Mscorwert. dll</span><span class="sxs-lookup"><span data-stu-id="530a8-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="530a8-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="530a8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="530a8-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="530a8-115">See also</span></span>

- [<span data-ttu-id="530a8-116">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="530a8-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
