---
title: _AxlGetIssuerPublicKeyHash-Funktion
ms.date: 03/30/2017
api_name:
- _AxlGetIssuerPublicKeyHash
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: fb626b41-b888-4625-84c3-2c02b5e3866f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 408b71bf38427d12418e05f8b509fe841bc95ef1
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43395233"
---
# <a name="axlgetissuerpublickeyhash-function"></a><span data-ttu-id="6ff47-102">_AxlGetIssuerPublicKeyHash-Funktion</span><span class="sxs-lookup"><span data-stu-id="6ff47-102">_AxlGetIssuerPublicKeyHash Function</span></span>
<span data-ttu-id="6ff47-103">Ruft den SHA-1-Hash des öffentlichen Schlüssels ab, der dem privaten Schlüssel zugeordnet wurde, der beim Signieren des festgelegten Zertifikats zur Verwendung kam.</span><span class="sxs-lookup"><span data-stu-id="6ff47-103">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ff47-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6ff47-104">Syntax</span></span>  
  
```  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6ff47-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6ff47-105">Parameters</span></span>  
 `pChainContext`  
 <span data-ttu-id="6ff47-106">[in] Der CSP-BLOB des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="6ff47-106">[in] The CSP public key blob.</span></span> <span data-ttu-id="6ff47-107">Finden Sie unter den [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) Struktur.</span><span class="sxs-lookup"><span data-stu-id="6ff47-107">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="6ff47-108">[out] Ein Zeiger auf WCHAR \* zum Erhalt des hexadezimal codierten öffentlichen Schlüsseltokens.</span><span class="sxs-lookup"><span data-stu-id="6ff47-108">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ff47-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6ff47-109">Return Value</span></span>  
 <span data-ttu-id="6ff47-110">`S_OK`, wenn die Funktion erfolgreich ausgeführt wird, sonst `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="6ff47-110">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ff47-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ff47-111">See Also</span></span>  
 [<span data-ttu-id="6ff47-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="6ff47-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
