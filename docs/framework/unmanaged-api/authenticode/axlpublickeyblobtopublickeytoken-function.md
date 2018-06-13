---
title: _AxlPublicKeyBlobToPublicKeyToken-Funktion
ms.date: 03/30/2017
api_name:
- _AxlPublicKeyBlobToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 2d92a746-d68c-4f53-a16e-727f071a2d80
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 56333165d179abd79e82f1416342a2700029eb12
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401673"
---
# <a name="axlpublickeyblobtopublickeytoken-function"></a><span data-ttu-id="14830-102">_AxlPublicKeyBlobToPublicKeyToken-Funktion</span><span class="sxs-lookup"><span data-stu-id="14830-102">_AxlPublicKeyBlobToPublicKeyToken Function</span></span>
<span data-ttu-id="14830-103">Berechnet den starken Namen des öffentlichen Schlüsseltokens aus einem CSP PUBLICKEYBLOB-Format.</span><span class="sxs-lookup"><span data-stu-id="14830-103">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14830-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="14830-104">Syntax</span></span>  
  
```  
HRESULT _AxlPublicKeyBlobToPublicKeyToken (  
    [in]  PCCERT_CHAIN_CONTEXT   pCspPublicKeyBlob,  
    [out] LPWSTR                 *ppwszPublicKeyToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="14830-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="14830-105">Parameters</span></span>  
 `pCspPublicKeyBlob`  
 <span data-ttu-id="14830-106">[in] Der CSP-BLOB des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="14830-106">[in] The CSP public key blob.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="14830-107">[out] Ein Zeiger auf WCHAR \*, um den hexadezimal codierten Hash für den öffentlichen Schlüssel zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="14830-107">[out] A pointer to WCHAR \* to receive the hex-encoded public key hash.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14830-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="14830-108">Return Value</span></span>  
 <span data-ttu-id="14830-109">`S_OK`, wenn die Funktion erfolgreich ausgeführt wird, sonst `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="14830-109">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14830-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14830-110">See Also</span></span>  
 [<span data-ttu-id="14830-111">Authenticode</span><span class="sxs-lookup"><span data-stu-id="14830-111">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
