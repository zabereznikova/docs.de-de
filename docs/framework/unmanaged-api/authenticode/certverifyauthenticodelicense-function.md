---
title: CertVerifyAuthenticodeLicense-Funktion
ms.date: 03/30/2017
api_name:
- CertVerifyAuthenticodeLicense
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 00118de7-33c6-41c4-8e1f-5d5e35e0da83
ms.openlocfilehash: 388814d1c63f048c0aa231a1d0058a390cba9493
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674059"
---
# <a name="certverifyauthenticodelicense-function"></a><span data-ttu-id="1039a-102">CertVerifyAuthenticodeLicense-Funktion</span><span class="sxs-lookup"><span data-stu-id="1039a-102">CertVerifyAuthenticodeLicense Function</span></span>

<span data-ttu-id="1039a-103">Überprüft die Gültigkeit einer Authenticode-XrML-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="1039a-103">Verifies the validity of an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1039a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1039a-104">Syntax</span></span>  
  
```cpp  
HRESULT CertVerifyAuthenticodeLicense (  
    [in]   PCRYPT_DATA_BLOB                   pLicenseBlob,  
    [in]   OPTIONAL DWORD                     dwFlags,  
    [out]  PAXL_AUTHENTICODE_SIGNER_INFO      pSignerInfo,  
    [out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1039a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1039a-105">Parameters</span></span>  

 `pLicenseBlob`  
 <span data-ttu-id="1039a-106">[in] Die Authenticode-XrML-Lizenz, die überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="1039a-106">[in] The Authenticode XrML license to be verified.</span></span>  
  
 <span data-ttu-id="1039a-107">Siehe [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) Struktur.</span><span class="sxs-lookup"><span data-stu-id="1039a-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="1039a-108">[in] Optional.</span><span class="sxs-lookup"><span data-stu-id="1039a-108">[in] Optional.</span></span> <span data-ttu-id="1039a-109">Eine Kombination der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="1039a-109">A combination of following values:</span></span>  
  
- <span data-ttu-id="1039a-110">AXL_REVOCATION_NO_CHECK</span><span class="sxs-lookup"><span data-stu-id="1039a-110">AXL_REVOCATION_NO_CHECK</span></span>  
  
- <span data-ttu-id="1039a-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span><span class="sxs-lookup"><span data-stu-id="1039a-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span></span>  
  
- <span data-ttu-id="1039a-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span><span class="sxs-lookup"><span data-stu-id="1039a-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span></span>  
  
- <span data-ttu-id="1039a-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span><span class="sxs-lookup"><span data-stu-id="1039a-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span></span>  
  
- <span data-ttu-id="1039a-114">AXL_LIFETIME_SIGNING</span><span class="sxs-lookup"><span data-stu-id="1039a-114">AXL_LIFETIME_SIGNING</span></span>  
  
- <span data-ttu-id="1039a-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span><span class="sxs-lookup"><span data-stu-id="1039a-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span></span>  
  
 `pSignerInfo`  
 <span data-ttu-id="1039a-116">[out] Für den Erhalt von Informationen über den Signaturgeber.</span><span class="sxs-lookup"><span data-stu-id="1039a-116">[out] To receive the signer's information.</span></span> <span data-ttu-id="1039a-117">Wenn die Lizenz nicht signiert wurde, ist `dwError` auf TRUST_E_NOSIGNATURE eingestellt.</span><span class="sxs-lookup"><span data-stu-id="1039a-117">If the license wasn't signed, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="1039a-118">Es liegt in der Verantwortung des Aufrufers, mithilfe der [CertFreeAuthenticodeSignerInfo](certfreeauthenticodesignerinfo-function.md) -Funktion Ressourcen freizugeben, nachdem er verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="1039a-118">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeSignerInfo](certfreeauthenticodesignerinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="1039a-119">Siehe [AXL_AUTHENTICODE_SIGNER_INFO Struktur](axl-authenticode-signer-info-structure.md).</span><span class="sxs-lookup"><span data-stu-id="1039a-119">See [AXL_AUTHENTICODE_SIGNER_INFO Structure](axl-authenticode-signer-info-structure.md).</span></span>  
  
 `pTimestamperInfo`  
 <span data-ttu-id="1039a-120">[out] Für den Erhalt von Informationen über den Ersteller des Zeitstempels, wenn verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1039a-120">[out] To receive time stamper's information, if available.</span></span> <span data-ttu-id="1039a-121">Wenn die Lizenz keinen Zeitstempel erhalten hat, ist `dwError` auf TRUST_E_NOSIGNATURE eingestellt.</span><span class="sxs-lookup"><span data-stu-id="1039a-121">If the license was not time-stamped, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="1039a-122">Es liegt in der Verantwortung des Aufrufers, Ressourcen mithilfe der [certfreeauthenticodetimestamperinfo](certfreeauthenticodetimestamperinfo-function.md) -Funktion nach der Verwendung freizugeben.</span><span class="sxs-lookup"><span data-stu-id="1039a-122">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeTimestamperInfo](certfreeauthenticodetimestamperinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="1039a-123">Siehe [AXL_AUTHENTICODE_TIMESTAMPER_INFO Struktur](axl-authenticode-timestamper-info-structure.md).</span><span class="sxs-lookup"><span data-stu-id="1039a-123">See [AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure](axl-authenticode-timestamper-info-structure.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1039a-124">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1039a-124">Return Value</span></span>  

 <span data-ttu-id="1039a-125">Gibt bei Erfolg `S_OK` zurück.</span><span class="sxs-lookup"><span data-stu-id="1039a-125">Returns `S_OK` if successful.</span></span> <span data-ttu-id="1039a-126">Andernfalls wird ein Fehlercode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1039a-126">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1039a-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1039a-127">See also</span></span>

- [<span data-ttu-id="1039a-128">Authenticode</span><span class="sxs-lookup"><span data-stu-id="1039a-128">Authenticode</span></span>](index.md)
- [<span data-ttu-id="1039a-129">GetHashFromHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="1039a-129">GetHashFromHandle Method</span></span>](../hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="1039a-130">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1039a-130">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
