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
ms.openlocfilehash: 42f5685a9a976be7a3a73badf286f77216e43106
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741243"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="45772-102">CertFreeAuthenticodeSignerInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="45772-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="45772-103">Gibt zugeordnete Ressourcen frei, die [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) Struktur.</span><span class="sxs-lookup"><span data-stu-id="45772-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45772-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="45772-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45772-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="45772-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="45772-106">[in, out] Informationen über den Signaturgeber die veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="45772-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="45772-107">Finden Sie unter den [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) Struktur.</span><span class="sxs-lookup"><span data-stu-id="45772-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="45772-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="45772-108">Return Value</span></span>  
 <span data-ttu-id="45772-109">`S_OK`, wenn die Funktion erfolgreich ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="45772-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="45772-110">Andernfalls wird ein Fehlercode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="45772-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45772-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45772-111">See also</span></span>

- [<span data-ttu-id="45772-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="45772-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
