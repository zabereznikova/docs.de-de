---
title: ICLRStrongName::GetHashFromFile-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.GetHashFromFile
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::GetHashFromFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromFile method [.NET Framework hosting]
- GetHashFromFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 9e50480a-8ada-4044-b2a5-97bb14ed3525
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 480113148e039ff1be3e438b4af2e24fdeacba14
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamegethashfromfile-method"></a><span data-ttu-id="f6252-102">ICLRStrongName::GetHashFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="f6252-102">ICLRStrongName::GetHashFromFile Method</span></span>
<span data-ttu-id="f6252-103">Generiert einen Hash des Inhalts der angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="f6252-103">Generates a hash over the contents of the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6252-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f6252-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f6252-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f6252-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="f6252-106">[in] Der Name der Datei für den Hash.</span><span class="sxs-lookup"><span data-stu-id="f6252-106">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="f6252-107">[in, out] Der Algorithmus beim Generieren des Hashs verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f6252-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="f6252-108">Gültige Algorithmen sind diejenigen, die von Win32 Crypto-API definiert.</span><span class="sxs-lookup"><span data-stu-id="f6252-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="f6252-109">Wenn `piHashAlg` ist auf 0 festgelegt, der Standardalgorithmus CALG_SHA-1 verwendet.</span><span class="sxs-lookup"><span data-stu-id="f6252-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="f6252-110">[out] Ein Bytearray, das den generierten Hash enthält.</span><span class="sxs-lookup"><span data-stu-id="f6252-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="f6252-111">[in] Die maximale Größe des Puffers, `pbHash` verweist auf.</span><span class="sxs-lookup"><span data-stu-id="f6252-111">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="f6252-112">[out] Die Größe in Bytes, der zurückgegebenen `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="f6252-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6252-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f6252-113">Return Value</span></span>  
 <span data-ttu-id="f6252-114">`S_OK`Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [häufig auftretende HRESULT-Werte](http://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="f6252-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6252-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f6252-115">Remarks</span></span>  
 <span data-ttu-id="f6252-116">Diese Methode ist identisch mit der [ICLRStrongName:: GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) -Methode, außer dass der name der Datei Spezifikation ist ANSI anstelle von Unicode.</span><span class="sxs-lookup"><span data-stu-id="f6252-116">This method is the same as the [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) method, except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6252-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f6252-117">Requirements</span></span>  
 <span data-ttu-id="f6252-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6252-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6252-119">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="f6252-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f6252-120">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f6252-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f6252-121">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6252-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6252-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6252-122">See Also</span></span>  
 [<span data-ttu-id="f6252-123">GetHashFromFileW-Methode</span><span class="sxs-lookup"><span data-stu-id="f6252-123">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)  
 [<span data-ttu-id="f6252-124">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f6252-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
