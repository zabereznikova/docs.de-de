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
ms.openlocfilehash: 355e6c7b1cd77936d5ccfa5ccff7312c8e35ac63
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220399"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="8ae16-102">CertFreeAuthenticodeTimestamperInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="8ae16-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="8ae16-103">Gibt zugeordnete Ressourcen frei, die [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) Struktur.</span><span class="sxs-lookup"><span data-stu-id="8ae16-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ae16-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ae16-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ae16-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8ae16-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="8ae16-106">[in, out] Informationen über den Ersteller des Zeitstempels, die veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8ae16-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="8ae16-107">Finden Sie unter den [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) Struktur.</span><span class="sxs-lookup"><span data-stu-id="8ae16-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ae16-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8ae16-108">Return Value</span></span>  
 `S_OK` <span data-ttu-id="8ae16-109">wenn die Funktion erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8ae16-109">if the function succeeds.</span></span> <span data-ttu-id="8ae16-110">Andernfalls wird ein Fehlercode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8ae16-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ae16-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ae16-111">See also</span></span>

- [<span data-ttu-id="8ae16-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="8ae16-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
