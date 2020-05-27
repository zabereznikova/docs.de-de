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
ms.openlocfilehash: ee5dd611888ec52e360ef45fab4c01e9c5b2d6bb
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009448"
---
# <a name="waitortimercallback-function-pointer"></a><span data-ttu-id="ff597-102">WAITORTIMERCALLBACK-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="ff597-102">WAITORTIMERCALLBACK Function Pointer</span></span>
<span data-ttu-id="ff597-103">Verweist auf eine Funktion, die den Host benachrichtigt, dass ein Wait-Handle ( <xref:System.Threading.WaitHandle> ) entweder signalisiert wurde oder ein Timeout aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="ff597-103">Points to a function that notifies the host that a wait handle (<xref:System.Threading.WaitHandle>) has either been signaled or timed out.</span></span>  
  
 <span data-ttu-id="ff597-104">Dieser Funktionszeiger wurde in der .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="ff597-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff597-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ff597-105">Syntax</span></span>  
  
```cpp  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff597-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ff597-106">Parameters</span></span>  
 `lpParameter`  
 <span data-ttu-id="ff597-107">in Ein Zeiger auf ein Objekt, das vom Host definierte Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="ff597-107">[in] A pointer to an object that contains information defined by the host.</span></span>  
  
 `TimerOrWaitFired`  
 <span data-ttu-id="ff597-108">[in] `true` , wenn das Wait-Handle abgelaufen ist, oder, `false` Wenn es signalisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ff597-108">[in] `true` if the wait handle timed out, or `false` if it was signaled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff597-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ff597-109">Remarks</span></span>  
 <span data-ttu-id="ff597-110">Die Funktion, auf die `WAITORTIMERCALLBACK` verweist, ist eine Rückruffunktion und muss vom Writer der Hostinganwendung implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="ff597-110">The function to which `WAITORTIMERCALLBACK` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff597-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ff597-111">Requirements</span></span>  
 <span data-ttu-id="ff597-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff597-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff597-113">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="ff597-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ff597-114">**Bibliothek:** Mscorwert. dll</span><span class="sxs-lookup"><span data-stu-id="ff597-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="ff597-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff597-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff597-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff597-116">See also</span></span>

- [<span data-ttu-id="ff597-117">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="ff597-117">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
