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
ms.openlocfilehash: 448712561f1531a055ac141db9825581525c779c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59106703"
---
# <a name="axlgetissuerpublickeyhash-function"></a><span data-ttu-id="39dcc-102">_AxlGetIssuerPublicKeyHash-Funktion</span><span class="sxs-lookup"><span data-stu-id="39dcc-102">_AxlGetIssuerPublicKeyHash Function</span></span>
<span data-ttu-id="39dcc-103">Ruft den SHA-1-Hash des öffentlichen Schlüssels ab, der dem privaten Schlüssel zugeordnet wurde, der beim Signieren des festgelegten Zertifikats zur Verwendung kam.</span><span class="sxs-lookup"><span data-stu-id="39dcc-103">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39dcc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="39dcc-104">Syntax</span></span>  
  
```  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39dcc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="39dcc-105">Parameters</span></span>  
 `pChainContext`  
 <span data-ttu-id="39dcc-106">[in] Der Blob für den öffentlichen CSP-Schlüssel</span><span class="sxs-lookup"><span data-stu-id="39dcc-106">[in] The CSP public key blob.</span></span> <span data-ttu-id="39dcc-107">Finden Sie unter den [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) Struktur.</span><span class="sxs-lookup"><span data-stu-id="39dcc-107">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="39dcc-108">[out] Ein Zeiger auf WCHAR \*, um den hexadezimal codierten öffentlichen Schlüsseltoken zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="39dcc-108">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39dcc-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="39dcc-109">Return Value</span></span>  
 <span data-ttu-id="39dcc-110">`S_OK`,wenn die Funktion erfolgreich ausgeführt wird, sonst `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="39dcc-110">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39dcc-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39dcc-111">See also</span></span>

- [<span data-ttu-id="39dcc-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="39dcc-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
