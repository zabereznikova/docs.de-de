---
title: CertFreeAuthenticodeTimestamperInfo-Funktion
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeTimestamperInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 3eb14c49-68c2-4516-ac89-e5bd7473831c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 27c16cb5d85ddffc1646bee893c5644682812025
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560580"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="2c6d0-102">CertFreeAuthenticodeTimestamperInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="2c6d0-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="2c6d0-103">Gibt zugeordnete Ressourcen frei, die [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) Struktur.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c6d0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c6d0-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2c6d0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2c6d0-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="2c6d0-106">[in, out] Informationen über den Ersteller des Zeitstempels, die veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="2c6d0-107">Finden Sie unter den [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) Struktur.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c6d0-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2c6d0-108">Return Value</span></span>  
 <span data-ttu-id="2c6d0-109">`S_OK`, wenn die Funktion erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="2c6d0-110">Andernfalls wird ein Fehlercode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c6d0-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c6d0-111">See also</span></span>
- [<span data-ttu-id="2c6d0-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="2c6d0-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
