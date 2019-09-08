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
ms.openlocfilehash: 357a2ca0ffc733adb14a21624cbe28fb754c8240
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776730"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="6fd2c-102">CertFreeAuthenticodeSignerInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="6fd2c-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="6fd2c-103">Gibt Ressourcen frei, die der [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) -Struktur zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="6fd2c-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fd2c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6fd2c-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fd2c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6fd2c-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="6fd2c-106">[in, out] Informationen über den Signaturgeber die veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6fd2c-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="6fd2c-107">Siehe [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) -Struktur.</span><span class="sxs-lookup"><span data-stu-id="6fd2c-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6fd2c-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6fd2c-108">Return Value</span></span>  
 <span data-ttu-id="6fd2c-109">`S_OK`, wenn die Funktion erfolgreich ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="6fd2c-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="6fd2c-110">Andernfalls wird ein Fehlercode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6fd2c-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fd2c-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6fd2c-111">See also</span></span>

- [<span data-ttu-id="6fd2c-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="6fd2c-112">Authenticode</span></span>](index.md)
