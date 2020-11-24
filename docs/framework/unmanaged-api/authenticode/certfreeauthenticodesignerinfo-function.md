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
ms.openlocfilehash: dc6bb5a137a50ec07f89f292e5d9beac4349c3c7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674176"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="d2cc3-102">CertFreeAuthenticodeSignerInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="d2cc3-102">CertFreeAuthenticodeSignerInfo Function</span></span>

<span data-ttu-id="d2cc3-103">Gibt Ressourcen frei, die der [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) Struktur zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="d2cc3-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2cc3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2cc3-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2cc3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d2cc3-105">Parameters</span></span>  

 `pSignerInfo`  
 <span data-ttu-id="d2cc3-106">[in, out] Informationen über den Signaturgeber die veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d2cc3-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="d2cc3-107">Siehe [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) Struktur.</span><span class="sxs-lookup"><span data-stu-id="d2cc3-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2cc3-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d2cc3-108">Return Value</span></span>  

 <span data-ttu-id="d2cc3-109">`S_OK`, wenn die Funktion erfolgreich ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="d2cc3-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="d2cc3-110">Andernfalls wird ein Fehlercode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d2cc3-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2cc3-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d2cc3-111">See also</span></span>

- [<span data-ttu-id="d2cc3-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="d2cc3-112">Authenticode</span></span>](index.md)
