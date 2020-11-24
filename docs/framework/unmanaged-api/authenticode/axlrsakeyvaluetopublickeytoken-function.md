---
title: _AxlRSAKeyValueToPublicKeyToken-Funktion
ms.date: 03/30/2017
api_name:
- _AxlRSAKeyValueToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d60f19fe-7bec-47ba-b60e-ba9ce66abf8c
ms.openlocfilehash: 5c1e2bfc7fd55e807af68744e28faa473daea772
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674215"
---
# <a name="_axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="400b3-102">\_Axlrsakeyvaluetopublickeytoken-Funktion</span><span class="sxs-lookup"><span data-stu-id="400b3-102">\_AxlRSAKeyValueToPublicKeyToken function</span></span>

<span data-ttu-id="400b3-103">Konvertiert einen Modulo und Exponenten in einen starken Namen des öffentlichen Schlüsseltokens.</span><span class="sxs-lookup"><span data-stu-id="400b3-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="400b3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="400b3-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="400b3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="400b3-105">Parameters</span></span>  

 `pModulusBlob`  
 <span data-ttu-id="400b3-106">in Das Base64-codierte Modulus-BLOB (aus dem- \<Modulus> Element).</span><span class="sxs-lookup"><span data-stu-id="400b3-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="400b3-107">Siehe [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) Struktur.</span><span class="sxs-lookup"><span data-stu-id="400b3-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="400b3-108">in Der Base64-codierte Exponent-BLOB (aus dem- \<Exponent> Element).</span><span class="sxs-lookup"><span data-stu-id="400b3-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="400b3-109">Siehe [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) Struktur.</span><span class="sxs-lookup"><span data-stu-id="400b3-109">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="400b3-110">[out] Ein Zeiger auf WCHAR \*, um den hexadezimal codierten öffentlichen Schlüsseltoken zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="400b3-110">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="400b3-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="400b3-111">Return Value</span></span>  

 <span data-ttu-id="400b3-112">`S_OK`, wenn die Funktion erfolgreich ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="400b3-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="400b3-113">Andernfalls wird ein Fehlercode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="400b3-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="400b3-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="400b3-114">See also</span></span>

- [<span data-ttu-id="400b3-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="400b3-115">Authenticode</span></span>](index.md)
