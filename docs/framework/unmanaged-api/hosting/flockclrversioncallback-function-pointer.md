---
title: FLockClrVersionCallback-Funktionszeiger
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FLockClrVersionCallback
api_location: mscoree.dll
api_type: COM
f1_keywords: FLockClrVersionCallback
helpviewer_keywords: FLockClrVersionCallback function pointer [.NET Framework hosting]
ms.assetid: 98a4762d-9ad2-45bd-9d03-39064a028b44
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca1b97c509ea8ed2c43c30cab278048aeb4170a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="ed42f-102">FLockClrVersionCallback-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="ed42f-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="ed42f-103">Zeigt auf eine Funktion, die die common Language Runtime (CLR) Ruft auf, um anzugeben, dass die Initialisierung gestartet oder abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="ed42f-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="ed42f-104">Diese Funktionszeiger ist veraltet die [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed42f-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed42f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ed42f-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="ed42f-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ed42f-106">Remarks</span></span>  
 <span data-ttu-id="ed42f-107">Diese Funktion wird vom Host implementiert.</span><span class="sxs-lookup"><span data-stu-id="ed42f-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed42f-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ed42f-108">Requirements</span></span>  
 <span data-ttu-id="ed42f-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed42f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed42f-110">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ed42f-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ed42f-111">**Bibliothek:** "Mscorwks.dll"</span><span class="sxs-lookup"><span data-stu-id="ed42f-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="ed42f-112">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed42f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed42f-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed42f-113">See Also</span></span>  
 [<span data-ttu-id="ed42f-114">LockClrVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="ed42f-114">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 [<span data-ttu-id="ed42f-115">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="ed42f-115">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
