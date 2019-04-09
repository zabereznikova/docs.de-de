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
ms.openlocfilehash: 49476a4417e5431842f8e2ba0371c53c5c9f03e9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207824"
---
# <a name="axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="2b9e5-102">\_AxlRSAKeyValueToPublicKeyToken-Funktion</span><span class="sxs-lookup"><span data-stu-id="2b9e5-102">\_AxlRSAKeyValueToPublicKeyToken function</span></span>

<span data-ttu-id="2b9e5-103">Konvertiert einen Modulo und Exponenten in einen starken Namen des öffentlichen Schlüsseltokens.</span><span class="sxs-lookup"><span data-stu-id="2b9e5-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b9e5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b9e5-104">Syntax</span></span>  
  
```  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b9e5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2b9e5-105">Parameters</span></span>  
 `pModulusBlob`  
 <span data-ttu-id="2b9e5-106">[in] Der base64-codierte Modulo-Blob (aus der \<Modulus > Element).</span><span class="sxs-lookup"><span data-stu-id="2b9e5-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="2b9e5-107">Finden Sie unter den [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) Struktur.</span><span class="sxs-lookup"><span data-stu-id="2b9e5-107">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="2b9e5-108">[in] Der base64-codierte Exponenten-Blob (aus der \<Exponent > Element).</span><span class="sxs-lookup"><span data-stu-id="2b9e5-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="2b9e5-109">Finden Sie unter den [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) Struktur.</span><span class="sxs-lookup"><span data-stu-id="2b9e5-109">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="2b9e5-110">[out] Ein Zeiger auf WCHAR \*, um den hexadezimal codierten öffentlichen Schlüsseltoken zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2b9e5-110">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2b9e5-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2b9e5-111">Return Value</span></span>  
 `S_OK` <span data-ttu-id="2b9e5-112">wenn die Funktion erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2b9e5-112">if the function succeeds.</span></span> <span data-ttu-id="2b9e5-113">Andernfalls wird ein Fehlercode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2b9e5-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b9e5-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b9e5-114">See also</span></span>

- [<span data-ttu-id="2b9e5-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="2b9e5-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
