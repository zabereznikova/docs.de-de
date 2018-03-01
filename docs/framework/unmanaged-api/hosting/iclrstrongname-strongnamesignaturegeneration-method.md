---
title: ICLRStrongName::StrongNameSignatureGeneration-Methode
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
- ICLRStrongName.StrongNameSignatureGeneration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureGeneration method [.NET Framework hosting]
ms.assetid: 4cdb1284-947a-4ed4-94c1-c5ff5cdfce56
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fcf872dcd1de34aaade06cf26914a75ae971b85b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a><span data-ttu-id="39c0b-102">ICLRStrongName::StrongNameSignatureGeneration-Methode</span><span class="sxs-lookup"><span data-stu-id="39c0b-102">ICLRStrongName::StrongNameSignatureGeneration Method</span></span>
<span data-ttu-id="39c0b-103">Generiert eine starke Namenssignatur für die angegebene Assembly an.</span><span class="sxs-lookup"><span data-stu-id="39c0b-103">Generates a strong name signature for the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39c0b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="39c0b-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureGeneration (   
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="39c0b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="39c0b-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="39c0b-106">[in] Der Pfad zur Datei, die das Manifest der Assembly enthält, für die Signatur des starken Namens generiert wird.</span><span class="sxs-lookup"><span data-stu-id="39c0b-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="39c0b-107">[in] Der Name des Schlüsselcontainers an, die das öffentlich/privat-Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="39c0b-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="39c0b-108">Wenn `pbKeyBlob` ist null, `wszKeyContainer` müssen einen gültigen Container innerhalb der Kryptografiedienstanbieter (CSP) angeben.</span><span class="sxs-lookup"><span data-stu-id="39c0b-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="39c0b-109">In diesem Fall wird das Schlüsselpaar in dem Container gespeichert verwendet, um die Datei zu signieren.</span><span class="sxs-lookup"><span data-stu-id="39c0b-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="39c0b-110">Wenn `pbKeyBlob` ist ungleich null, das Schlüsselpaar wird davon ausgegangen, dass im Schlüssel binary large Object (BLOB) enthalten sein soll.</span><span class="sxs-lookup"><span data-stu-id="39c0b-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="39c0b-111">Die Schlüssel müssen 1024-Bit-Rivest-Shamir-Adleman (RSA) Signaturschlüssel sein.</span><span class="sxs-lookup"><span data-stu-id="39c0b-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="39c0b-112">Zu diesem Zeitpunkt werden keine anderen Arten von Schlüsseln unterstützt.</span><span class="sxs-lookup"><span data-stu-id="39c0b-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="39c0b-113">[in] Ein Zeiger auf das öffentlich/privat-Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="39c0b-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="39c0b-114">Dieses Paar weist das Format, das erstellt wird, durch die Win32- `CryptExportKey` Funktion.</span><span class="sxs-lookup"><span data-stu-id="39c0b-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="39c0b-115">Wenn `pbKeyBlob` null ist, die vom angegebenen Schlüsselcontainer `wszKeyContainer` wird davon ausgegangen, dass das Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="39c0b-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="39c0b-116">[in] Die Größe in Bytes, der `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="39c0b-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="39c0b-117">[out] Ein Zeiger auf den Speicherort, an dem die common Language Runtime die Signatur zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="39c0b-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="39c0b-118">Wenn `ppbSignatureBlob` ist null, die Common Language Runtime speichert-Signatur in der Datei gemäß `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="39c0b-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="39c0b-119">Wenn `ppbSignatureBlob` ist ungleich null, die common Language Runtime reserviert Speicherplatz in dem die Signatur zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="39c0b-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="39c0b-120">Der Aufrufer muss diesen Speicherplatz freigeben, mithilfe der [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="39c0b-120">The caller must free this space by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="39c0b-121">[out] Die Größe in Bytes, der zurückgegebenen Signatur.</span><span class="sxs-lookup"><span data-stu-id="39c0b-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39c0b-122">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="39c0b-122">Return Value</span></span>  
 <span data-ttu-id="39c0b-123">`S_OK`Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [häufig auftretende HRESULT-Werte](http://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="39c0b-123">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39c0b-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="39c0b-124">Remarks</span></span>  
 <span data-ttu-id="39c0b-125">Geben Sie null für `wszFilePath` auf die Größe der Signatur zu berechnen, ohne die Signatur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="39c0b-125">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="39c0b-126">Die Signatur kann entweder direkt in der Datei gespeichert oder an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="39c0b-126">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39c0b-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="39c0b-127">Requirements</span></span>  
 <span data-ttu-id="39c0b-128">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39c0b-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39c0b-129">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="39c0b-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="39c0b-130">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="39c0b-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="39c0b-131">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39c0b-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39c0b-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39c0b-132">See Also</span></span>  
 [<span data-ttu-id="39c0b-133">StrongNameSignatureGenerationEx-Methode</span><span class="sxs-lookup"><span data-stu-id="39c0b-133">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)  
 [<span data-ttu-id="39c0b-134">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="39c0b-134">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
