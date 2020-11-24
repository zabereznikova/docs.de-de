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
ms.openlocfilehash: 989e99198efd1519f607a2e3164ff4de584e88af
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679883"
---
# <a name="_axlpublickeyblobtopublickeytoken-function"></a><span data-ttu-id="0f562-102">\_Axlpublickeyblobtopublickeytoken-Funktion</span><span class="sxs-lookup"><span data-stu-id="0f562-102">\_AxlPublicKeyBlobToPublicKeyToken Function</span></span>

<span data-ttu-id="0f562-103">Berechnet das öffentliche Schlüsseltoken für einen starken Namen aus einem CSP PUBLICKEYBLOB-Format.</span><span class="sxs-lookup"><span data-stu-id="0f562-103">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f562-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f562-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlPublicKeyBlobToPublicKeyToken (  
    [in]  PCCERT_CHAIN_CONTEXT   pCspPublicKeyBlob,  
    [out] LPWSTR                 *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f562-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0f562-105">Parameters</span></span>  

 `pCspPublicKeyBlob`  
 <span data-ttu-id="0f562-106">[in] Der Blob für den öffentlichen CSP-Schlüssel</span><span class="sxs-lookup"><span data-stu-id="0f562-106">[in] The CSP public key blob.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="0f562-107">[out] Ein Zeiger auf WCHAR \*, um den hexadezimal codierten Hash für den öffentlichen Schlüssel zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0f562-107">[out] A pointer to WCHAR \* to receive the hex-encoded public key hash.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f562-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0f562-108">Return Value</span></span>  

 <span data-ttu-id="0f562-109">`S_OK`,wenn die Funktion erfolgreich ausgeführt wird, sonst `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="0f562-109">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f562-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0f562-110">See also</span></span>

- [<span data-ttu-id="0f562-111">Authenticode</span><span class="sxs-lookup"><span data-stu-id="0f562-111">Authenticode</span></span>](index.md)
