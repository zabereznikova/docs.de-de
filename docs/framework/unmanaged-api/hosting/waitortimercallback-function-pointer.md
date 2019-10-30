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
ms.openlocfilehash: db6a20dee21b6c8bbd55fa9b52a159a00fe310d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092039"
---
# <a name="waitortimercallback-function-pointer"></a><span data-ttu-id="aa822-102">WAITORTIMERCALLBACK-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="aa822-102">WAITORTIMERCALLBACK Function Pointer</span></span>
<span data-ttu-id="aa822-103">Verweist auf eine Funktion, die den Host benachrichtigt, dass ein Wait-Handle (<xref:System.Threading.WaitHandle>) entweder signalisiert oder abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="aa822-103">Points to a function that notifies the host that a wait handle (<xref:System.Threading.WaitHandle>) has either been signaled or timed out.</span></span>  
  
 <span data-ttu-id="aa822-104">Dieser Funktionszeiger wurde in der .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="aa822-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa822-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa822-105">Syntax</span></span>  
  
```cpp  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa822-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="aa822-106">Parameters</span></span>  
 `lpParameter`  
 <span data-ttu-id="aa822-107">in Ein Zeiger auf ein Objekt, das vom Host definierte Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="aa822-107">[in] A pointer to an object that contains information defined by the host.</span></span>  
  
 `TimerOrWaitFired`  
 <span data-ttu-id="aa822-108">[in] `true`, wenn das Wait-Handle abgelaufen ist, oder `false`, wenn es signalisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="aa822-108">[in] `true` if the wait handle timed out, or `false` if it was signaled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa822-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aa822-109">Remarks</span></span>  
 <span data-ttu-id="aa822-110">Die Funktion, zu der `WAITORTIMERCALLBACK` Punkte eine Rückruffunktion ist und vom Writer der Hostinganwendung implementiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="aa822-110">The function to which `WAITORTIMERCALLBACK` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa822-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="aa822-111">Requirements</span></span>  
 <span data-ttu-id="aa822-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa822-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa822-113">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="aa822-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aa822-114">**Bibliothek:** Mscorwert. dll</span><span class="sxs-lookup"><span data-stu-id="aa822-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="aa822-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa822-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa822-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa822-116">See also</span></span>

- [<span data-ttu-id="aa822-117">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="aa822-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
