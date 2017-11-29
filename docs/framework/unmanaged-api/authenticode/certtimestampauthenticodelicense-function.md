---
title: CertTimestampAuthenticodeLicense-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CertTimestampAuthenticodeLicense
api_location: clr.dll
api_type: DLLExport
ms.assetid: d468325a-21c5-43ce-8567-84e342b22308
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 42ec863e9accbd2156b6eeed5857ff86075cf0a5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="certtimestampauthenticodelicense-function"></a><span data-ttu-id="bddf2-102">CertTimestampAuthenticodeLicense-Funktion</span><span class="sxs-lookup"><span data-stu-id="bddf2-102">CertTimestampAuthenticodeLicense Function</span></span>
<span data-ttu-id="bddf2-103">Fügt einer Authenticode-XrML-Lizenz einen Zeitstempel hinzu.</span><span class="sxs-lookup"><span data-stu-id="bddf2-103">Time-stamps an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bddf2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bddf2-104">Syntax</span></span>  
  
```  
HRESULT CertTimestampAuthenticodeLicense (  
    [in]  PCRYPT_DATA_BLOB   pSignedLicenseBlob,  
    [in]  LPCWSTR            pwszTimestampURI,  
    [out] PCRYPT_DATA_BLOB   pTimestampSignatureBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bddf2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bddf2-105">Parameters</span></span>  
 `pSignedLicenseBlob`  
 <span data-ttu-id="bddf2-106">[in] Die signierte Authenticode-XrML-Lizenz, die einen Zeitstempel erhalten soll.</span><span class="sxs-lookup"><span data-stu-id="bddf2-106">[in] The signed Authenticode XrML license to be time-stamped.</span></span> <span data-ttu-id="bddf2-107">Finden Sie unter der [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) Struktur.</span><span class="sxs-lookup"><span data-stu-id="bddf2-107">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `pwszTimestampURI`  
 <span data-ttu-id="bddf2-108">[in] Die URL des Zeitstempelservers.</span><span class="sxs-lookup"><span data-stu-id="bddf2-108">[in] The time-stamp server's URI.</span></span>  
  
 `pTimestampSignatureBlob`  
 <span data-ttu-id="bddf2-109">[out] Ein Zeiger auf CRYPT_DATA_BLOB, um die Base64-codierte Zeitstempelsignatur zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="bddf2-109">[out] A pointer to CRYPT_DATA_BLOB to receive the base64-encoded time-stamp signature.</span></span> <span data-ttu-id="bddf2-110">Es ist Aufgabe des Aufrufers frei `pTimestampSignatureBlob` -> `pbData` mit `HepFree()` nach ihrer Verwendung.</span><span class="sxs-lookup"><span data-stu-id="bddf2-110">It is the caller's responsibility to free `pTimestampSignatureBlob`->`pbData` with `HepFree()` after use.</span></span> <span data-ttu-id="bddf2-111">Finden Sie unter der [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) Struktur.</span><span class="sxs-lookup"><span data-stu-id="bddf2-111">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bddf2-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bddf2-112">Remarks</span></span>  
 <span data-ttu-id="bddf2-113">Die Zeitstempelsignatur ist eigentlich eine PKCS #7-SignedData-Nachricht, deren Inhalt die Binärform des SignatureValue aus der Signatur der Lizenz ist.</span><span class="sxs-lookup"><span data-stu-id="bddf2-113">The time-stamp signature is actually a PKCS #7 SignedData message whose content is the binary form of the SignatureValue from the license's signature.</span></span> <span data-ttu-id="bddf2-114">Im Prinzip agiert sie als Gegensignatur für die Lizenz.</span><span class="sxs-lookup"><span data-stu-id="bddf2-114">Basically, this acts as a counter-signature of the license.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bddf2-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bddf2-115">Return Value</span></span>  
 <span data-ttu-id="bddf2-116">`S_OK`, wenn die Funktion erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bddf2-116">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="bddf2-117">Andernfalls wird ein Fehlercode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bddf2-117">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bddf2-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bddf2-118">See Also</span></span>  
 [<span data-ttu-id="bddf2-119">Authenticode</span><span class="sxs-lookup"><span data-stu-id="bddf2-119">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
