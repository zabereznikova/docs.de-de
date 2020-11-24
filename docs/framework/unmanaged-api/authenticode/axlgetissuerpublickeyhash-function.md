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
ms.openlocfilehash: 49674e43109108e41b135cecbec061ad61e14865
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679961"
---
# <a name="_axlgetissuerpublickeyhash-function"></a><span data-ttu-id="1e37d-102">\_AxlGetIssuerPublicKeyHash-Funktion</span><span class="sxs-lookup"><span data-stu-id="1e37d-102">\_AxlGetIssuerPublicKeyHash Function</span></span>

<span data-ttu-id="1e37d-103">Ruft den SHA-1-Hash des öffentlichen Schlüssels ab, der dem privaten Schlüssel zugeordnet wurde, der beim Signieren des festgelegten Zertifikats zur Verwendung kam.</span><span class="sxs-lookup"><span data-stu-id="1e37d-103">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e37d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1e37d-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e37d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1e37d-105">Parameters</span></span>  

 `pChainContext`  
 <span data-ttu-id="1e37d-106">[in] Der Blob für den öffentlichen CSP-Schlüssel</span><span class="sxs-lookup"><span data-stu-id="1e37d-106">[in] The CSP public key blob.</span></span> <span data-ttu-id="1e37d-107">Siehe [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) Struktur.</span><span class="sxs-lookup"><span data-stu-id="1e37d-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="1e37d-108">[out] Ein Zeiger auf WCHAR \*, um den hexadezimal codierten öffentlichen Schlüsseltoken zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1e37d-108">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1e37d-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1e37d-109">Return Value</span></span>  

 <span data-ttu-id="1e37d-110">`S_OK`,wenn die Funktion erfolgreich ausgeführt wird, sonst `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="1e37d-110">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e37d-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1e37d-111">See also</span></span>

- [<span data-ttu-id="1e37d-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="1e37d-112">Authenticode</span></span>](index.md)
