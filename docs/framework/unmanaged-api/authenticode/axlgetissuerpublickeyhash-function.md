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
ms.openlocfilehash: 1cfc2f5cde22bf63275dd4bdc65857ac1d51b3fe
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038432"
---
# <a name="_axlgetissuerpublickeyhash-function"></a><span data-ttu-id="655f3-102">\_AxlGetIssuerPublicKeyHash-Funktion</span><span class="sxs-lookup"><span data-stu-id="655f3-102">\_AxlGetIssuerPublicKeyHash Function</span></span>
<span data-ttu-id="655f3-103">Ruft den SHA-1-Hash des öffentlichen Schlüssels ab, der dem privaten Schlüssel zugeordnet wurde, der beim Signieren des festgelegten Zertifikats zur Verwendung kam.</span><span class="sxs-lookup"><span data-stu-id="655f3-103">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="655f3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="655f3-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="655f3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="655f3-105">Parameters</span></span>  
 `pChainContext`  
 <span data-ttu-id="655f3-106">[in] Der Blob für den öffentlichen CSP-Schlüssel</span><span class="sxs-lookup"><span data-stu-id="655f3-106">[in] The CSP public key blob.</span></span> <span data-ttu-id="655f3-107">Siehe [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) -Struktur.</span><span class="sxs-lookup"><span data-stu-id="655f3-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="655f3-108">[out] Ein Zeiger auf WCHAR \*, um den hexadezimal codierten öffentlichen Schlüsseltoken zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="655f3-108">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="655f3-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="655f3-109">Return Value</span></span>  
 <span data-ttu-id="655f3-110">`S_OK`,wenn die Funktion erfolgreich ausgeführt wird, sonst `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="655f3-110">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="655f3-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="655f3-111">See also</span></span>

- [<span data-ttu-id="655f3-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="655f3-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
