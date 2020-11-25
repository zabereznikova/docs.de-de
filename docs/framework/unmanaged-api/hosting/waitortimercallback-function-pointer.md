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
ms.openlocfilehash: 74256f35804ff59f04952a1ac20ac7866e8f5683
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732813"
---
# <a name="waitortimercallback-function-pointer"></a><span data-ttu-id="e41f2-102">WAITORTIMERCALLBACK-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="e41f2-102">WAITORTIMERCALLBACK Function Pointer</span></span>

<span data-ttu-id="e41f2-103">Verweist auf eine Funktion, die den Host benachrichtigt, dass ein Wait-Handle ( <xref:System.Threading.WaitHandle> ) entweder signalisiert wurde oder ein Timeout aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="e41f2-103">Points to a function that notifies the host that a wait handle (<xref:System.Threading.WaitHandle>) has either been signaled or timed out.</span></span>  
  
 <span data-ttu-id="e41f2-104">Dieser Funktionszeiger wurde in der .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="e41f2-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e41f2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e41f2-105">Syntax</span></span>  
  
```cpp  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e41f2-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e41f2-106">Parameters</span></span>  

 `lpParameter`  
 <span data-ttu-id="e41f2-107">in Ein Zeiger auf ein Objekt, das vom Host definierte Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="e41f2-107">[in] A pointer to an object that contains information defined by the host.</span></span>  
  
 `TimerOrWaitFired`  
 <span data-ttu-id="e41f2-108">[in] `true` , wenn das Wait-Handle abgelaufen ist, oder, `false` Wenn es signalisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="e41f2-108">[in] `true` if the wait handle timed out, or `false` if it was signaled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e41f2-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e41f2-109">Remarks</span></span>  

 <span data-ttu-id="e41f2-110">Die Funktion, auf die `WAITORTIMERCALLBACK` verweist, ist eine Rückruffunktion und muss vom Writer der Hostinganwendung implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="e41f2-110">The function to which `WAITORTIMERCALLBACK` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e41f2-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e41f2-111">Requirements</span></span>  

 <span data-ttu-id="e41f2-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e41f2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e41f2-113">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="e41f2-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e41f2-114">**Bibliothek:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="e41f2-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="e41f2-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e41f2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e41f2-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e41f2-116">See also</span></span>

- [<span data-ttu-id="e41f2-117">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="e41f2-117">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
