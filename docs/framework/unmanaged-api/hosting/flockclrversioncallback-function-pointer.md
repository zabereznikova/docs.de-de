---
title: FLockClrVersionCallback-Funktionszeiger
ms.date: 03/30/2017
api_name:
- FLockClrVersionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FLockClrVersionCallback
helpviewer_keywords:
- FLockClrVersionCallback function pointer [.NET Framework hosting]
ms.assetid: 98a4762d-9ad2-45bd-9d03-39064a028b44
topic_type:
- apiref
ms.openlocfilehash: f1ad414c30788801e14a33e98a0893e2a0f58d0c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136520"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="db331-102">FLockClrVersionCallback-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="db331-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="db331-103">Verweist auf eine Funktion, die vom Common Language Runtime (CLR) aufgerufen wird, um anzugeben, dass die Initialisierung entweder gestartet oder abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="db331-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="db331-104">Dieser Funktionszeiger wurde in der .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="db331-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db331-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="db331-105">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="db331-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="db331-106">Remarks</span></span>  
 <span data-ttu-id="db331-107">Diese Funktion wird vom Host implementiert.</span><span class="sxs-lookup"><span data-stu-id="db331-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db331-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="db331-108">Requirements</span></span>  
 <span data-ttu-id="db331-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db331-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db331-110">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="db331-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="db331-111">**Bibliothek:** Mscorwert. dll</span><span class="sxs-lookup"><span data-stu-id="db331-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="db331-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db331-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db331-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db331-113">See also</span></span>

- [<span data-ttu-id="db331-114">LockClrVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="db331-114">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)
- [<span data-ttu-id="db331-115">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="db331-115">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
