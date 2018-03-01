---
title: GetAppIdAuthority-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- GetAppIdAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetAppIdAuthority
helpviewer_keywords:
- GetAppIdAuthority function [.NET Framework fusion]
ms.assetid: 9f968dad-0d09-47fb-bebc-94c39a0d16ad
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0e89624feb04050534b917b865d5cb53b8c4cf58
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="getappidauthority-function"></a><span data-ttu-id="6a273-102">GetAppIdAuthority-Funktion</span><span class="sxs-lookup"><span data-stu-id="6a273-102">GetAppIdAuthority Function</span></span>
<span data-ttu-id="6a273-103">Ruft einen Zeiger auf eine [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) -Instanz, die Schlüssel für Anwendungsidentitäten und Verweise verwaltet.</span><span class="sxs-lookup"><span data-stu-id="6a273-103">Gets a pointer to an [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) instance that manages keys for application identities and references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a273-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6a273-104">Syntax</span></span>  
  
```  
HRESULT GetAppIdAuthority (  
    [out] IAppIdAuthority **ppIAppIdAuthority  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6a273-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6a273-105">Parameters</span></span>  
 `ppIAppIdAuthority`  
 <span data-ttu-id="6a273-106">[out] Das zurückgegebene `IAppIdAuthority` Zeiger.</span><span class="sxs-lookup"><span data-stu-id="6a273-106">[out] The returned `IAppIdAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a273-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6a273-107">Requirements</span></span>  
 <span data-ttu-id="6a273-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a273-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a273-109">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="6a273-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="6a273-110">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a273-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a273-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a273-111">See Also</span></span>  
 [<span data-ttu-id="6a273-112">IAppIdAuthority-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6a273-112">IAppIdAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md)  
 [<span data-ttu-id="6a273-113">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="6a273-113">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
