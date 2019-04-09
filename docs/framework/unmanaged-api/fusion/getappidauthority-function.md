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
ms.openlocfilehash: 274b91793cd51348c42661bf12a4e4385e17f630
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093968"
---
# <a name="getappidauthority-function"></a><span data-ttu-id="ebbcd-102">GetAppIdAuthority-Funktion</span><span class="sxs-lookup"><span data-stu-id="ebbcd-102">GetAppIdAuthority Function</span></span>
<span data-ttu-id="ebbcd-103">Ruft einen Zeiger auf ein [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) -Instanz, die Schlüssel für Anwendungsidentitäten und Verweise verwaltet.</span><span class="sxs-lookup"><span data-stu-id="ebbcd-103">Gets a pointer to an [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) instance that manages keys for application identities and references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebbcd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ebbcd-104">Syntax</span></span>  
  
```  
HRESULT GetAppIdAuthority (  
    [out] IAppIdAuthority **ppIAppIdAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebbcd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ebbcd-105">Parameters</span></span>  
 `ppIAppIdAuthority`  
 <span data-ttu-id="ebbcd-106">[out] Das zurückgegebene `IAppIdAuthority` Zeiger.</span><span class="sxs-lookup"><span data-stu-id="ebbcd-106">[out] The returned `IAppIdAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebbcd-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ebbcd-107">Requirements</span></span>  
 <span data-ttu-id="ebbcd-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebbcd-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebbcd-109">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="ebbcd-109">**Header:** Isolation.h</span></span>  
  
 **<span data-ttu-id="ebbcd-110">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="ebbcd-110">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ebbcd-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ebbcd-111">See also</span></span>

- [<span data-ttu-id="ebbcd-112">IAppIdAuthority-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ebbcd-112">IAppIdAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md)
- [<span data-ttu-id="ebbcd-113">Fusion – Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="ebbcd-113">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
