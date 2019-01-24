---
title: GetAppIdAuthority-Funktion
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c45da047d384e56440ca5f883a4cfd755a7d0299
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54719711"
---
# <a name="getappidauthority-function"></a><span data-ttu-id="1c39e-102">GetAppIdAuthority-Funktion</span><span class="sxs-lookup"><span data-stu-id="1c39e-102">GetAppIdAuthority Function</span></span>
<span data-ttu-id="1c39e-103">Ruft einen Zeiger auf ein [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) -Instanz, die Schlüssel für Anwendungsidentitäten und Verweise verwaltet.</span><span class="sxs-lookup"><span data-stu-id="1c39e-103">Gets a pointer to an [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) instance that manages keys for application identities and references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c39e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1c39e-104">Syntax</span></span>  
  
```  
HRESULT GetAppIdAuthority (  
    [out] IAppIdAuthority **ppIAppIdAuthority  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1c39e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1c39e-105">Parameters</span></span>  
 `ppIAppIdAuthority`  
 <span data-ttu-id="1c39e-106">[out] Das zurückgegebene `IAppIdAuthority` Zeiger.</span><span class="sxs-lookup"><span data-stu-id="1c39e-106">[out] The returned `IAppIdAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c39e-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1c39e-107">Requirements</span></span>  
 <span data-ttu-id="1c39e-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c39e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c39e-109">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="1c39e-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="1c39e-110">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c39e-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c39e-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c39e-111">See also</span></span>
- [<span data-ttu-id="1c39e-112">IAppIdAuthority-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1c39e-112">IAppIdAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md)
- [<span data-ttu-id="1c39e-113">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="1c39e-113">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
