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
ms.openlocfilehash: 9c37a9af6a1532d03fa04ca151605cef7ab5244e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401767"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="b9870-102">CertFreeAuthenticodeTimestamperInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="b9870-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="b9870-103">Macht Ressourcen frei der [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) Struktur.</span><span class="sxs-lookup"><span data-stu-id="b9870-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9870-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b9870-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9870-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b9870-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="b9870-106">[in, out] Informationen über den Ersteller des Zeitstempels, die veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b9870-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="b9870-107">Finden Sie unter der [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) Struktur.</span><span class="sxs-lookup"><span data-stu-id="b9870-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9870-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b9870-108">Return Value</span></span>  
 <span data-ttu-id="b9870-109">`S_OK`, wenn die Funktion erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b9870-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="b9870-110">Andernfalls wird ein Fehlercode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b9870-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9870-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9870-111">See Also</span></span>  
 [<span data-ttu-id="b9870-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="b9870-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
