---
title: ICLRStrongName::GetHashFromBlob-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromBlob
helpviewer_keywords:
- ICLRStrongName::GetHashFromBlob method [.NET Framework hosting]
- GetHashFromBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: f91d0f89-f356-49ac-aafb-50fad963c13d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ca958f8472d7f7e1a44ad4ab237f582f92713c3
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43402737"
---
# <a name="iclrstrongnamegethashfromblob-method"></a><span data-ttu-id="6a31d-102">ICLRStrongName::GetHashFromBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="6a31d-102">ICLRStrongName::GetHashFromBlob Method</span></span>
<span data-ttu-id="6a31d-103">Ruft einen Hash der Assembly an der angegebenen Speicheradresse, die unter Verwendung des angegebenen Hashalgorithmus ab.</span><span class="sxs-lookup"><span data-stu-id="6a31d-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a31d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6a31d-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromBlob (  
    [in]  BYTE    *pbBlob,  
    [in]  DWORD   cchBlob,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE    *pbHash,  
    [in]  DWORD   cchHash,  
    [out] DWORD   *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6a31d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6a31d-105">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="6a31d-106">[in] Ein Zeiger auf die Adresse des Speicherblocks, der Hashwert berechnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6a31d-106">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="6a31d-107">[in] Die Länge des Speicherblocks in Bytes.</span><span class="sxs-lookup"><span data-stu-id="6a31d-107">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="6a31d-108">[in, out] Eine Konstante, die den Hashalgorithmus angibt.</span><span class="sxs-lookup"><span data-stu-id="6a31d-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="6a31d-109">Verwenden Sie 0 (null), für den Standardalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="6a31d-109">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="6a31d-110">[out] Der zurückgegebene Hashpuffer.</span><span class="sxs-lookup"><span data-stu-id="6a31d-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="6a31d-111">[in] Die angeforderte maximale Größe des `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="6a31d-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="6a31d-112">[out] Die Größe in Bytes, des zurückgegebenen `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="6a31d-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6a31d-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6a31d-113">Return Value</span></span>  
 <span data-ttu-id="6a31d-114">`S_OK` Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="6a31d-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a31d-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6a31d-115">Requirements</span></span>  
 <span data-ttu-id="6a31d-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a31d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a31d-117">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="6a31d-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6a31d-118">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6a31d-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6a31d-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a31d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a31d-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a31d-120">See Also</span></span>  
 [<span data-ttu-id="6a31d-121">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6a31d-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
