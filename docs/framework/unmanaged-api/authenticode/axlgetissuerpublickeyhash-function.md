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
ms.openlocfilehash: b197aa539e60a9dbcee55cf190c44b45da3a5fb4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402014"
---
# <a name="axlgetissuerpublickeyhash-function"></a><span data-ttu-id="5b6f7-102">_AxlGetIssuerPublicKeyHash-Funktion</span><span class="sxs-lookup"><span data-stu-id="5b6f7-102">_AxlGetIssuerPublicKeyHash Function</span></span>
<span data-ttu-id="5b6f7-103">Ruft den SHA-1-Hash des öffentlichen Schlüssels ab, der dem privaten Schlüssel zugeordnet wurde, der beim Signieren des festgelegten Zertifikats zur Verwendung kam.</span><span class="sxs-lookup"><span data-stu-id="5b6f7-103">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b6f7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5b6f7-104">Syntax</span></span>  
  
```  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5b6f7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5b6f7-105">Parameters</span></span>  
 `pChainContext`  
 <span data-ttu-id="5b6f7-106">[in] Der CSP-BLOB des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="5b6f7-106">[in] The CSP public key blob.</span></span> <span data-ttu-id="5b6f7-107">Finden Sie unter der [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) Struktur.</span><span class="sxs-lookup"><span data-stu-id="5b6f7-107">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="5b6f7-108">[out] Ein Zeiger auf WCHAR \* zum Erhalt des hexadezimal codierten öffentlichen Schlüsseltokens.</span><span class="sxs-lookup"><span data-stu-id="5b6f7-108">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b6f7-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5b6f7-109">Return Value</span></span>  
 <span data-ttu-id="5b6f7-110">`S_OK`, wenn die Funktion erfolgreich ausgeführt wird, sonst `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="5b6f7-110">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b6f7-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b6f7-111">See Also</span></span>  
 [<span data-ttu-id="5b6f7-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="5b6f7-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
