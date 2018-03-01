---
title: ICLRStrongName::GetHashFromAssemblyFileW-Methode
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
- ICLRStrongName.GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW method [.NET Framework hosting]
- GetHashFromAssemblyFileW method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5d0b44a2-5a14-44a2-9a0e-e8682fd4e106
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b10d74cd54afc3c93578710d4a2e339a1f8761f3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a><span data-ttu-id="ca73f-102">ICLRStrongName::GetHashFromAssemblyFileW-Methode</span><span class="sxs-lookup"><span data-stu-id="ca73f-102">ICLRStrongName::GetHashFromAssemblyFileW Method</span></span>
<span data-ttu-id="ca73f-103">Generiert einen Hash des Inhalts der Datei durch eine Unicode-Zeichenfolge angegeben.</span><span class="sxs-lookup"><span data-stu-id="ca73f-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca73f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ca73f-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ca73f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ca73f-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="ca73f-106">[in] Der Pfad zu der Datei, der Hashwert berechnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ca73f-106">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="ca73f-107">Dieser Parameter muss eine Unicode-Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="ca73f-107">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="ca73f-108">[in, out] Eine Konstante, die den Hashalgorithmus angibt.</span><span class="sxs-lookup"><span data-stu-id="ca73f-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="ca73f-109">Verwenden Sie 0 (null), für die Standard-Hash-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="ca73f-109">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="ca73f-110">[out] Der zurückgegebene Hashpuffer.</span><span class="sxs-lookup"><span data-stu-id="ca73f-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="ca73f-111">[in] Die angeforderte maximale Größe der `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="ca73f-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="ca73f-112">[out] Die Größe in Bytes, der zurückgegebenen `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="ca73f-112">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca73f-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ca73f-113">Return Value</span></span>  
 <span data-ttu-id="ca73f-114">`S_OK`Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [häufig auftretende HRESULT-Werte](http://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="ca73f-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca73f-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ca73f-115">Requirements</span></span>  
 <span data-ttu-id="ca73f-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca73f-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca73f-117">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="ca73f-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ca73f-118">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ca73f-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca73f-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca73f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca73f-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca73f-120">See Also</span></span>  
 [<span data-ttu-id="ca73f-121">GetHashFromAssemblyFile-Methode</span><span class="sxs-lookup"><span data-stu-id="ca73f-121">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)  
 [<span data-ttu-id="ca73f-122">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ca73f-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
