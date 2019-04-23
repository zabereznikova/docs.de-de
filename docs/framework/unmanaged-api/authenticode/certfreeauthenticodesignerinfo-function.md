---
title: CertFreeAuthenticodeSignerInfo-Funktion
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeSignerInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 8029633c-b6e4-4665-a7c2-89607c3247ef
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bdb764417b757cd7388c49d7e5cac9a960074820
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142401"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="ca05c-102">CertFreeAuthenticodeSignerInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="ca05c-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="ca05c-103">Gibt zugeordnete Ressourcen frei, die [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) Struktur.</span><span class="sxs-lookup"><span data-stu-id="ca05c-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca05c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ca05c-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca05c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ca05c-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="ca05c-106">[in, out] Informationen über den Signaturgeber die veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ca05c-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="ca05c-107">Finden Sie unter den [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) Struktur.</span><span class="sxs-lookup"><span data-stu-id="ca05c-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca05c-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ca05c-108">Return Value</span></span>  
 <span data-ttu-id="ca05c-109">`S_OK`, wenn die Funktion erfolgreich ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="ca05c-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="ca05c-110">Andernfalls wird ein Fehlercode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ca05c-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca05c-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca05c-111">See also</span></span>

- [<span data-ttu-id="ca05c-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="ca05c-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
