---
title: ICLRStrongName::StrongNameTokenFromAssemblyEx-Methode
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
- ICLRStrongName.StrongNameTokenFromAssemblyEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameTokenFromAssemblyEx method [.NET Framework hosting]
ms.assetid: 648ea90e-5e60-40a0-a56a-3e61bf2fba7c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5b8b3437d8c07cd57a4791995890cab1b06aafc6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnametokenfromassemblyex-method"></a><span data-ttu-id="beb31-102">ICLRStrongName::StrongNameTokenFromAssemblyEx-Methode</span><span class="sxs-lookup"><span data-stu-id="beb31-102">ICLRStrongName::StrongNameTokenFromAssemblyEx Method</span></span>
<span data-ttu-id="beb31-103">Erstellt ein Token mit starkem Namen aus der angegebenen Assemblydatei und gibt den öffentlichen Schlüssel, den das Token darstellt.</span><span class="sxs-lookup"><span data-stu-id="beb31-103">Creates a strong name token from the specified assembly file, and returns the public key that the token represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="beb31-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="beb31-104">Syntax</span></span>  
  
```  
HRESULT StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="beb31-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="beb31-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="beb31-106">[in] Der Pfad zur Datei (portable Executable)-Datei für die Assembly.</span><span class="sxs-lookup"><span data-stu-id="beb31-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="beb31-107">[out] Das zurückgegebene strong Name-Token.</span><span class="sxs-lookup"><span data-stu-id="beb31-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="beb31-108">[out] Die Größe in Bytes, der das Token mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="beb31-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="beb31-109">[out] Der zurückgegebene öffentliche Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="beb31-109">[out] The returned public key.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="beb31-110">[out] Die Größe in Bytes, des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="beb31-110">[out] The size, in bytes, of the public key.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="beb31-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="beb31-111">Return Value</span></span>  
 <span data-ttu-id="beb31-112">`S_OK`Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [häufig auftretende HRESULT-Werte](http://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="beb31-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="beb31-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="beb31-113">Remarks</span></span>  
 <span data-ttu-id="beb31-114">Ein starker Name-Token ist die Kurzform eines öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="beb31-114">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="beb31-115">Das Token ist ein 64-Bit-Hash, der aus dem öffentlichen Schlüssel zum Signieren der Assembly erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="beb31-115">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="beb31-116">Das Token ist ein Teil des starken Namens für die Assembly und kann aus den Metadaten der Assembly gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="beb31-116">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="beb31-117">Nachdem der Schlüssel abgerufen und das Token wird erstellt, Sie sollten Aufrufen der [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) Methode, um den belegten Speicher freizugeben.</span><span class="sxs-lookup"><span data-stu-id="beb31-117">After the key is retrieved and the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="beb31-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="beb31-118">Requirements</span></span>  
 <span data-ttu-id="beb31-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="beb31-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="beb31-120">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="beb31-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="beb31-121">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="beb31-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="beb31-122">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="beb31-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beb31-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="beb31-123">See Also</span></span>  
 [<span data-ttu-id="beb31-124">StrongNameTokenFromAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="beb31-124">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)  
 [<span data-ttu-id="beb31-125">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="beb31-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
