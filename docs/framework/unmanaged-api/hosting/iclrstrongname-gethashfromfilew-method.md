---
title: ICLRStrongName::GetHashFromFileW-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRStrongName.GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromFileW method [.NET Framework hosting]
ms.assetid: c6ff45fc-905d-4c6e-b00c-97c6c7c55d99
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eec58e0cf062e405c757a506e9c26955009b710b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamegethashfromfilew-method"></a><span data-ttu-id="0b4ad-102">ICLRStrongName::GetHashFromFileW-Methode</span><span class="sxs-lookup"><span data-stu-id="0b4ad-102">ICLRStrongName::GetHashFromFileW Method</span></span>
<span data-ttu-id="0b4ad-103">Generiert einen Hash des Inhalts der Datei durch eine Unicode-Zeichenfolge angegeben.</span><span class="sxs-lookup"><span data-stu-id="0b4ad-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b4ad-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b4ad-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="0b4ad-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0b4ad-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="0b4ad-106">[in] Der Unicode-Name der Datei für den Hash.</span><span class="sxs-lookup"><span data-stu-id="0b4ad-106">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="0b4ad-107">[in, out] Der Algorithmus beim Generieren des Hashs verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0b4ad-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="0b4ad-108">Gültige Algorithmen sind diejenigen, die von Win32 Crypto-API definiert.</span><span class="sxs-lookup"><span data-stu-id="0b4ad-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="0b4ad-109">Wenn `piHashAlg` ist auf 0 festgelegt, der Standardalgorithmus CALG_SHA-1 verwendet.</span><span class="sxs-lookup"><span data-stu-id="0b4ad-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="0b4ad-110">[out] Ein Bytearray, das den generierten Hash enthält.</span><span class="sxs-lookup"><span data-stu-id="0b4ad-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="0b4ad-111">[in] Die maximale Größe des Puffers verweist `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="0b4ad-111">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="0b4ad-112">[out] Die Größe in Bytes, der `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="0b4ad-112">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b4ad-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0b4ad-113">Return Value</span></span>  
 <span data-ttu-id="0b4ad-114">`S_OK`Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [häufig auftretende HRESULT-Werte](http://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="0b4ad-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b4ad-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0b4ad-115">Remarks</span></span>  
 <span data-ttu-id="0b4ad-116">Diese Methode ist identisch mit der [ICLRStrongName:: GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) -Methode, außer dass der name der Datei Spezifikation Unicode anstelle von ANSI codiert ist.</span><span class="sxs-lookup"><span data-stu-id="0b4ad-116">This method is the same as the [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) method, except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b4ad-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0b4ad-117">Requirements</span></span>  
 <span data-ttu-id="0b4ad-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b4ad-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b4ad-119">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="0b4ad-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0b4ad-120">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0b4ad-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0b4ad-121">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b4ad-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b4ad-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b4ad-122">See Also</span></span>  
 [<span data-ttu-id="0b4ad-123">GetHashFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="0b4ad-123">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)  
 [<span data-ttu-id="0b4ad-124">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0b4ad-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
