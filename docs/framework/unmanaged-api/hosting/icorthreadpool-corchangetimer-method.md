---
title: ICorThreadpool::CorChangeTimer-Methode
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorChangeTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorChangeTimer
helpviewer_keywords:
- CorChangeTimer method [.NET Framework hosting]
- ICorThreadpool::CorChangeTimer method [.NET Framework hosting]
ms.assetid: 82b03a59-5a87-43ed-9b75-e04b256e1a46
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de4a61f188bc6419b52f168c8bbbf43ad91fa19e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700045"
---
# <a name="icorthreadpoolcorchangetimer-method"></a><span data-ttu-id="3df93-102">ICorThreadpool::CorChangeTimer-Methode</span><span class="sxs-lookup"><span data-stu-id="3df93-102">ICorThreadpool::CorChangeTimer Method</span></span>
<span data-ttu-id="3df93-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="3df93-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3df93-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3df93-104">Syntax</span></span>  
  
```  
HRESULT CorChangeTimer (  
    [in]  HANDLE Timer,   
    [in]  ULONG  DueTime,   
    [in]  ULONG  Period,  
    [out] BOOL*  result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="3df93-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3df93-105">Requirements</span></span>  
 <span data-ttu-id="3df93-106">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3df93-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3df93-107">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3df93-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3df93-108">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3df93-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3df93-109">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3df93-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3df93-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3df93-110">See also</span></span>

- [<span data-ttu-id="3df93-111">ICorThreadpool-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3df93-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
