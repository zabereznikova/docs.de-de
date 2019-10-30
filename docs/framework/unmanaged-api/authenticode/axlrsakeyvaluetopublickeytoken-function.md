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
ms.openlocfilehash: 1f53df33a65d3f75b7574eda3507e370c2e086ac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099816"
---
# <a name="_axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="61819-102">\_axlrsakeyvaluetopublickeytoken-Funktion</span><span class="sxs-lookup"><span data-stu-id="61819-102">\_AxlRSAKeyValueToPublicKeyToken function</span></span>

<span data-ttu-id="61819-103">Konvertiert einen Modulo und Exponenten in einen starken Namen des öffentlichen Schlüsseltokens.</span><span class="sxs-lookup"><span data-stu-id="61819-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61819-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="61819-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61819-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="61819-105">Parameters</span></span>  
 `pModulusBlob`  
 <span data-ttu-id="61819-106">in Das Base64-codierte Modulus-BLOB (aus dem \<Modulus >-Element).</span><span class="sxs-lookup"><span data-stu-id="61819-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="61819-107">Siehe [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) -Struktur.</span><span class="sxs-lookup"><span data-stu-id="61819-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="61819-108">in Der Base64-codierte Exponent-BLOB (aus dem \<Exponent >-Element).</span><span class="sxs-lookup"><span data-stu-id="61819-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="61819-109">Siehe [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) -Struktur.</span><span class="sxs-lookup"><span data-stu-id="61819-109">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="61819-110">[out] Ein Zeiger auf WCHAR \*, um den hexadezimal codierten öffentlichen Schlüsseltoken zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="61819-110">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61819-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="61819-111">Return Value</span></span>  
 <span data-ttu-id="61819-112">`S_OK`, wenn die Funktion erfolgreich ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="61819-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="61819-113">Andernfalls wird ein Fehlercode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="61819-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61819-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61819-114">See also</span></span>

- [<span data-ttu-id="61819-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="61819-115">Authenticode</span></span>](index.md)
