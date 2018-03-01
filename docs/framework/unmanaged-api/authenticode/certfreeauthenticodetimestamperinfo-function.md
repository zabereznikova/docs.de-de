---
title: CertFreeAuthenticodeTimestamperInfo-Funktion
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
- CertFreeAuthenticodeTimestamperInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 3eb14c49-68c2-4516-ac89-e5bd7473831c
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 353bba880cfa8a5ecf9ed826fbb529e31f790a12
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="4252e-102">CertFreeAuthenticodeTimestamperInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="4252e-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="4252e-103">Macht Ressourcen frei der [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) Struktur.</span><span class="sxs-lookup"><span data-stu-id="4252e-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4252e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4252e-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4252e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4252e-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="4252e-106">[in, out] Informationen über den Ersteller des Zeitstempels, die veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4252e-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="4252e-107">Finden Sie unter der [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) Struktur.</span><span class="sxs-lookup"><span data-stu-id="4252e-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4252e-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4252e-108">Return Value</span></span>  
 <span data-ttu-id="4252e-109">`S_OK`, wenn die Funktion erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4252e-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="4252e-110">Andernfalls wird ein Fehlercode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4252e-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4252e-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4252e-111">See Also</span></span>  
 [<span data-ttu-id="4252e-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="4252e-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
