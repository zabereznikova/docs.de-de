---
title: _AxlRSAKeyValueToPublicKeyToken-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _AxlRSAKeyValueToPublicKeyToken
api_location: clr.dll
api_type: DLLExport
ms.assetid: d60f19fe-7bec-47ba-b60e-ba9ce66abf8c
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4af27a2abf1a0bcf4d79eda389c5f79f0ecb1eef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="8b189-102">_AxlRSAKeyValueToPublicKeyToken-Funktion</span><span class="sxs-lookup"><span data-stu-id="8b189-102">_AxlRSAKeyValueToPublicKeyToken Function</span></span>
<span data-ttu-id="8b189-103">Konvertiert ein Modulo und einen Exponenten in ein Token für den öffentlichen Schlüssel für einen starken Namen.</span><span class="sxs-lookup"><span data-stu-id="8b189-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b189-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8b189-104">Syntax</span></span>  
  
```  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8b189-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8b189-105">Parameters</span></span>  
 `pModulusBlob`  
 <span data-ttu-id="8b189-106">[in] Die base64-codierte Modulo-Blob (aus der \<Modulus > Element).</span><span class="sxs-lookup"><span data-stu-id="8b189-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="8b189-107">Finden Sie unter der [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) Struktur.</span><span class="sxs-lookup"><span data-stu-id="8b189-107">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="8b189-108">[in] Die base64-codierte Exponenten-Blob (aus der \<Exponent > Element).</span><span class="sxs-lookup"><span data-stu-id="8b189-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="8b189-109">Finden Sie unter der [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) Struktur.</span><span class="sxs-lookup"><span data-stu-id="8b189-109">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="8b189-110">[out] Ein Zeiger auf WCHAR * zum Erhalt des hexadezimal codierten öffentlichen Schlüsseltokens.</span><span class="sxs-lookup"><span data-stu-id="8b189-110">[out] A pointer to WCHAR * to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8b189-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8b189-111">Return Value</span></span>  
 <span data-ttu-id="8b189-112">`S_OK`, wenn die Funktion erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8b189-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="8b189-113">Andernfalls wird ein Fehlercode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8b189-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b189-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b189-114">See Also</span></span>  
 [<span data-ttu-id="8b189-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="8b189-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
