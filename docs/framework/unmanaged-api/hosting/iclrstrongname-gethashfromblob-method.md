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
ms.openlocfilehash: 4a489e05435ce160c65e936f448688d69b3a965f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435260"
---
# <a name="iclrstrongnamegethashfromblob-method"></a><span data-ttu-id="aa870-102">ICLRStrongName::GetHashFromBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="aa870-102">ICLRStrongName::GetHashFromBlob Method</span></span>
<span data-ttu-id="aa870-103">Ruft einen Hash der Assembly an der angegebenen Speicheradresse, die mithilfe des angegebenen Hashalgorithmus ab.</span><span class="sxs-lookup"><span data-stu-id="aa870-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa870-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa870-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="aa870-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="aa870-105">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="aa870-106">[in] Ein Zeiger auf die Adresse des Speicherblocks, der Hashwert berechnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="aa870-106">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="aa870-107">[in] Die Länge des Speicherblocks in Bytes.</span><span class="sxs-lookup"><span data-stu-id="aa870-107">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="aa870-108">[in, out] Eine Konstante, die den Hashalgorithmus angibt.</span><span class="sxs-lookup"><span data-stu-id="aa870-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="aa870-109">Verwenden Sie 0 (null) für den Standardalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="aa870-109">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="aa870-110">[out] Der zurückgegebene Hashpuffer.</span><span class="sxs-lookup"><span data-stu-id="aa870-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="aa870-111">[in] Die angeforderte maximale Größe der `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="aa870-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="aa870-112">[out] Die Größe in Bytes, der zurückgegebenen `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="aa870-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aa870-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="aa870-113">Return Value</span></span>  
 <span data-ttu-id="aa870-114">`S_OK` Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [häufig auftretende HRESULT-Werte](http://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="aa870-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa870-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="aa870-115">Requirements</span></span>  
 <span data-ttu-id="aa870-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa870-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa870-117">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="aa870-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="aa870-118">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="aa870-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aa870-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa870-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa870-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa870-120">See Also</span></span>  
 [<span data-ttu-id="aa870-121">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aa870-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
