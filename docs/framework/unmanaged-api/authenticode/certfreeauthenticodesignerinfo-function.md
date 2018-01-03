---
title: CertFreeAuthenticodeSignerInfo-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CertFreeAuthenticodeSignerInfo
api_location: clr.dll
api_type: DLLExport
ms.assetid: 8029633c-b6e4-4665-a7c2-89607c3247ef
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f8b38d30a1323d0d44330b8bb9a006c372ea7780
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="8c068-102">CertFreeAuthenticodeSignerInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="8c068-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="8c068-103">Macht Ressourcen frei der [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) Struktur.</span><span class="sxs-lookup"><span data-stu-id="8c068-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c068-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8c068-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8c068-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8c068-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="8c068-106">[in, out] Informationen über den Signaturgeber, die veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8c068-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="8c068-107">Finden Sie unter der [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) Struktur.</span><span class="sxs-lookup"><span data-stu-id="8c068-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8c068-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8c068-108">Return Value</span></span>  
 <span data-ttu-id="8c068-109">`S_OK`, wenn die Funktion erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8c068-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="8c068-110">Andernfalls wird ein Fehlercode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8c068-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c068-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c068-111">See Also</span></span>  
 [<span data-ttu-id="8c068-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="8c068-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
