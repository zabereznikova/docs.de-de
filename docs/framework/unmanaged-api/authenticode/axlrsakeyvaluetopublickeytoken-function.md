---
title: _AxlRSAKeyValueToPublicKeyToken function
ms.date: 03/30/2017
api_name:
- _AxlRSAKeyValueToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d60f19fe-7bec-47ba-b60e-ba9ce66abf8c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a340af9ba196dbcd8618afdd83bcf7e56124bf7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54529907"
---
# <a name="axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="ab318-102">\_AxlRSAKeyValueToPublicKeyToken-Funktion</span><span class="sxs-lookup"><span data-stu-id="ab318-102">\_AxlRSAKeyValueToPublicKeyToken function</span></span>

<span data-ttu-id="ab318-103">Konvertiert ein Modulo und einen Exponenten in ein Token für den öffentlichen Schlüssel für einen starken Namen.</span><span class="sxs-lookup"><span data-stu-id="ab318-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab318-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ab318-104">Syntax</span></span>  
  
```  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
### <a name="parameters"></a><span data-ttu-id="ab318-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ab318-105">Parameters</span></span>  
 `pModulusBlob`  
 <span data-ttu-id="ab318-106">[in] Der base64-codierte Modulo-Blob (aus der \<Modulus > Element).</span><span class="sxs-lookup"><span data-stu-id="ab318-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="ab318-107">Finden Sie unter den [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) Struktur.</span><span class="sxs-lookup"><span data-stu-id="ab318-107">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="ab318-108">[in] Der base64-codierte Exponenten-Blob (aus der \<Exponent > Element).</span><span class="sxs-lookup"><span data-stu-id="ab318-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="ab318-109">Finden Sie unter den [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) Struktur.</span><span class="sxs-lookup"><span data-stu-id="ab318-109">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="ab318-110">[out] Ein Zeiger auf WCHAR \* zum Erhalt des hexadezimal codierten öffentlichen Schlüsseltokens.</span><span class="sxs-lookup"><span data-stu-id="ab318-110">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab318-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ab318-111">Return Value</span></span>  
 <span data-ttu-id="ab318-112">`S_OK`, wenn die Funktion erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ab318-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="ab318-113">Andernfalls wird ein Fehlercode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ab318-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab318-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab318-114">See also</span></span>
- [<span data-ttu-id="ab318-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="ab318-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
