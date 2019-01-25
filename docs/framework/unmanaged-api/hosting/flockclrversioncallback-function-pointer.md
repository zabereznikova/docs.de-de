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
ms.openlocfilehash: d25afe5ecc8dd23e78fd60fbf8452e28c5aa8be5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610590"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="25f8e-102">FLockClrVersionCallback-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="25f8e-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="25f8e-103">Verweist auf eine Funktion, die die common Language Runtime (CLR) Ruft auf, um anzugeben, dass die Initialisierung gestartet oder abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="25f8e-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="25f8e-104">Dieser Funktionszeiger ist veraltet, der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25f8e-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25f8e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="25f8e-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="25f8e-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="25f8e-106">Remarks</span></span>  
 <span data-ttu-id="25f8e-107">Diese Funktion wird vom Host implementiert.</span><span class="sxs-lookup"><span data-stu-id="25f8e-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25f8e-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="25f8e-108">Requirements</span></span>  
 <span data-ttu-id="25f8e-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25f8e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25f8e-110">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="25f8e-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="25f8e-111">**Bibliothek:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="25f8e-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="25f8e-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25f8e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25f8e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25f8e-113">See also</span></span>
- [<span data-ttu-id="25f8e-114">LockClrVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="25f8e-114">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)
- [<span data-ttu-id="25f8e-115">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="25f8e-115">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
