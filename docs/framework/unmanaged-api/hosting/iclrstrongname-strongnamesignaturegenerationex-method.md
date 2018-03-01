---
title: ICLRStrongName::StrongNameSignatureGenerationEx-Methode
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
- ICLRStrongName.StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx method [.NET Framework hosting]
- StrongNameSignatureGenerationEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: c3f34584-c6e2-41fd-bb44-e44da8546309
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 247bcfa3c9f7a02dea331ff14948a00812fb06e5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamesignaturegenerationex-method"></a><span data-ttu-id="63dbd-102">ICLRStrongName::StrongNameSignatureGenerationEx-Methode</span><span class="sxs-lookup"><span data-stu-id="63dbd-102">ICLRStrongName::StrongNameSignatureGenerationEx Method</span></span>
<span data-ttu-id="63dbd-103">Generiert eine starke Namenssignatur für die angegebene Assembly gemäß den angegebenen Flags.</span><span class="sxs-lookup"><span data-stu-id="63dbd-103">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63dbd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="63dbd-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="63dbd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="63dbd-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="63dbd-106">[in] Der Pfad zur Datei, die das Manifest der Assembly enthält, für die Signatur des starken Namens generiert wird.</span><span class="sxs-lookup"><span data-stu-id="63dbd-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="63dbd-107">[in] Der Name des Schlüsselcontainers an, die das öffentlich/privat-Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="63dbd-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="63dbd-108">Wenn `pbKeyBlob` ist null, `wszKeyContainer` müssen einen gültigen Container innerhalb der Kryptografiedienstanbieter (CSP) angeben.</span><span class="sxs-lookup"><span data-stu-id="63dbd-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="63dbd-109">In diesem Fall wird das Schlüsselpaar in dem Container gespeichert verwendet, um die Datei zu signieren.</span><span class="sxs-lookup"><span data-stu-id="63dbd-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="63dbd-110">Wenn `pbKeyBlob` ist ungleich null, das Schlüsselpaar wird davon ausgegangen, dass im Schlüssel binary large Object (BLOB) enthalten sein soll.</span><span class="sxs-lookup"><span data-stu-id="63dbd-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="63dbd-111">[in] Ein Zeiger auf das öffentlich/privat-Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="63dbd-111">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="63dbd-112">Dieses Paar weist das Format, das erstellt wird, durch die Win32- `CryptExportKey` Funktion.</span><span class="sxs-lookup"><span data-stu-id="63dbd-112">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="63dbd-113">Wenn `pbKeyBlob` null ist, die vom angegebenen Schlüsselcontainer `wszKeyContainer` wird davon ausgegangen, dass das Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="63dbd-113">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="63dbd-114">[in] Die Größe in Bytes, der `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="63dbd-114">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="63dbd-115">[out] Ein Zeiger auf den Speicherort, an dem die common Language Runtime die Signatur zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="63dbd-115">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="63dbd-116">Wenn `ppbSignatureBlob` ist null, die Common Language Runtime speichert-Signatur in der Datei gemäß `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="63dbd-116">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="63dbd-117">Wenn `ppbSignatureBlob` ist ungleich null, die common Language Runtime reserviert Speicherplatz in dem die Signatur zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="63dbd-117">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="63dbd-118">Der Aufrufer muss diesen Speicherplatz mit Freigeben der [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="63dbd-118">The caller must free this space using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="63dbd-119">[out] Die Größe in Bytes, der zurückgegebenen Signatur.</span><span class="sxs-lookup"><span data-stu-id="63dbd-119">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="63dbd-120">[in] Eine oder mehrere der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="63dbd-120">[in] One or more of the following values:</span></span>  
  
-   <span data-ttu-id="63dbd-121">`SN_SIGN_ALL_FILES`(0 x 00000001) – alle Hashes für verknüpfte Module neu.</span><span class="sxs-lookup"><span data-stu-id="63dbd-121">`SN_SIGN_ALL_FILES` (0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
-   <span data-ttu-id="63dbd-122">`SN_TEST_SIGN`(0 x 00000002) - Test Signierung der Assembly.</span><span class="sxs-lookup"><span data-stu-id="63dbd-122">`SN_TEST_SIGN` (0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63dbd-123">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="63dbd-123">Return Value</span></span>  
 <span data-ttu-id="63dbd-124">`S_OK`Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [häufig auftretende HRESULT-Werte](http://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="63dbd-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63dbd-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="63dbd-125">Remarks</span></span>  
 <span data-ttu-id="63dbd-126">Geben Sie null für `wszFilePath` auf die Größe der Signatur zu berechnen, ohne die Signatur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="63dbd-126">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="63dbd-127">Die Signatur kann werden entweder direkt in der Datei gespeichert oder an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="63dbd-127">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="63dbd-128">Wenn `SN_SIGN_ALL_FILES` angegeben ist, aber ein öffentlicher Schlüssel nicht enthalten ist (beide `pbKeyBlob` und `wszFilePath` sind null), werden Hashes für verknüpfte Module neu berechnet, aber die Assembly wird nicht erneut signiert.</span><span class="sxs-lookup"><span data-stu-id="63dbd-128">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="63dbd-129">Wenn `SN_TEST_SIGN` angegeben ist, wird die common Language Runtime-Header wird nicht geändert, um anzugeben, dass die Assembly mit einem starken Namen signiert ist.</span><span class="sxs-lookup"><span data-stu-id="63dbd-129">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63dbd-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="63dbd-130">Requirements</span></span>  
 <span data-ttu-id="63dbd-131">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63dbd-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63dbd-132">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="63dbd-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="63dbd-133">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="63dbd-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="63dbd-134">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63dbd-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63dbd-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63dbd-135">See Also</span></span>  
 [<span data-ttu-id="63dbd-136">StrongNameSignatureGeneration-Methode</span><span class="sxs-lookup"><span data-stu-id="63dbd-136">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)  
 [<span data-ttu-id="63dbd-137">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="63dbd-137">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
