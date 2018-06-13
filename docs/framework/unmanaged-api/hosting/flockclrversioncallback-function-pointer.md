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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c884d07fa35c053b1a3b65c04426ac0e3712621
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429672"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="4f246-102">FLockClrVersionCallback-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="4f246-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="4f246-103">Zeigt auf eine Funktion, die die common Language Runtime (CLR) Ruft auf, um anzugeben, dass die Initialisierung gestartet oder abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="4f246-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="4f246-104">Diese Funktionszeiger ist veraltet die [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f246-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f246-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4f246-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="4f246-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4f246-106">Remarks</span></span>  
 <span data-ttu-id="4f246-107">Diese Funktion wird vom Host implementiert.</span><span class="sxs-lookup"><span data-stu-id="4f246-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f246-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4f246-108">Requirements</span></span>  
 <span data-ttu-id="4f246-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f246-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f246-110">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4f246-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4f246-111">**Bibliothek:** "Mscorwks.dll"</span><span class="sxs-lookup"><span data-stu-id="4f246-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="4f246-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f246-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f246-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f246-113">See Also</span></span>  
 [<span data-ttu-id="4f246-114">LockClrVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="4f246-114">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 [<span data-ttu-id="4f246-115">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="4f246-115">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
