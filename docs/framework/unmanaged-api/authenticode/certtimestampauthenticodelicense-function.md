---
title: CertTimestampAuthenticodeLicense-Funktion
ms.date: 03/30/2017
api_name:
- CertTimestampAuthenticodeLicense
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d468325a-21c5-43ce-8567-84e342b22308
ms.openlocfilehash: fc1a99572406a38aee8133d6435134b78a134175
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674098"
---
# <a name="certtimestampauthenticodelicense-function"></a><span data-ttu-id="ceead-102">CertTimestampAuthenticodeLicense-Funktion</span><span class="sxs-lookup"><span data-stu-id="ceead-102">CertTimestampAuthenticodeLicense Function</span></span>

<span data-ttu-id="ceead-103">Fügt einer Authenticode-XrML-Lizenz einen Zeitstempel hinzu.</span><span class="sxs-lookup"><span data-stu-id="ceead-103">Time-stamps an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ceead-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ceead-104">Syntax</span></span>  
  
```cpp  
HRESULT CertTimestampAuthenticodeLicense (  
    [in]  PCRYPT_DATA_BLOB   pSignedLicenseBlob,  
    [in]  LPCWSTR            pwszTimestampURI,  
    [out] PCRYPT_DATA_BLOB   pTimestampSignatureBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ceead-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ceead-105">Parameters</span></span>  

 `pSignedLicenseBlob`  
 <span data-ttu-id="ceead-106">[in] Die signierte Authenticode-XrML-Lizenz, die einen Zeitstempel erhalten soll.</span><span class="sxs-lookup"><span data-stu-id="ceead-106">[in] The signed Authenticode XrML license to be time-stamped.</span></span> <span data-ttu-id="ceead-107">Siehe [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) Struktur.</span><span class="sxs-lookup"><span data-stu-id="ceead-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `pwszTimestampURI`  
 <span data-ttu-id="ceead-108">[in] Die URL des Zeitstempelservers.</span><span class="sxs-lookup"><span data-stu-id="ceead-108">[in] The time-stamp server's URI.</span></span>  
  
 `pTimestampSignatureBlob`  
 <span data-ttu-id="ceead-109">[out] Ein Zeiger auf CRYPT_DATA_BLOB, um die Base64-codierte Zeitstempelsignatur zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ceead-109">[out] A pointer to CRYPT_DATA_BLOB to receive the base64-encoded time-stamp signature.</span></span> <span data-ttu-id="ceead-110">Es liegt in der Verantwortung des Aufrufers, `pTimestampSignatureBlob` -> `pbData` nach Verwendung von freizugeben `HepFree()` .</span><span class="sxs-lookup"><span data-stu-id="ceead-110">It is the caller's responsibility to free `pTimestampSignatureBlob`->`pbData` with `HepFree()` after use.</span></span> <span data-ttu-id="ceead-111">Siehe [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) Struktur.</span><span class="sxs-lookup"><span data-stu-id="ceead-111">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ceead-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ceead-112">Remarks</span></span>  

 <span data-ttu-id="ceead-113">Die Zeitstempelsignatur ist eigentlich eine PKCS #7-SignedData-Nachricht, deren Inhalt die Binärform des SignatureValue aus der Signatur der Lizenz ist.</span><span class="sxs-lookup"><span data-stu-id="ceead-113">The time-stamp signature is actually a PKCS #7 SignedData message whose content is the binary form of the SignatureValue from the license's signature.</span></span> <span data-ttu-id="ceead-114">Im Prinzip agiert sie als Gegensignatur für die Lizenz.</span><span class="sxs-lookup"><span data-stu-id="ceead-114">Basically, this acts as a counter-signature of the license.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ceead-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ceead-115">Return Value</span></span>  

 <span data-ttu-id="ceead-116">`S_OK`, wenn die Funktion erfolgreich ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="ceead-116">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="ceead-117">Andernfalls wird ein Fehlercode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ceead-117">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceead-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ceead-118">See also</span></span>

- [<span data-ttu-id="ceead-119">Authenticode</span><span class="sxs-lookup"><span data-stu-id="ceead-119">Authenticode</span></span>](index.md)
