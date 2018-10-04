---
title: ICLRStrongName::StrongNameSignatureGenerationEx-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81f1eb4236bab72caf4421342e1f54d6d2f32607
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48776531"
---
# <a name="iclrstrongnamestrongnamesignaturegenerationex-method"></a><span data-ttu-id="5e176-102">ICLRStrongName::StrongNameSignatureGenerationEx-Methode</span><span class="sxs-lookup"><span data-stu-id="5e176-102">ICLRStrongName::StrongNameSignatureGenerationEx Method</span></span>
<span data-ttu-id="5e176-103">Generiert eine Signatur mit starkem Namen für die angegebene Assembly gemäß den angegebenen Flags.</span><span class="sxs-lookup"><span data-stu-id="5e176-103">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e176-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5e176-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="5e176-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5e176-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="5e176-106">[in] Der Pfad zur Datei, die das Manifest der Assembly enthält, für die Signatur mit starkem Namen generiert wird.</span><span class="sxs-lookup"><span data-stu-id="5e176-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="5e176-107">[in] Der Name des Schlüsselcontainers, die das öffentlich/privat-Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="5e176-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="5e176-108">Wenn `pbKeyBlob` null ist, `wszKeyContainer` müssen einen gültigen Container innerhalb der Kryptografiedienstanbieter (CSP) angeben.</span><span class="sxs-lookup"><span data-stu-id="5e176-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="5e176-109">In diesem Fall dient das Schlüsselpaar im Container gespeicherten zum Signieren der Datei.</span><span class="sxs-lookup"><span data-stu-id="5e176-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="5e176-110">Wenn `pbKeyBlob` ist nicht null ist, das Schlüsselpaar wird davon ausgegangen, dass im Schlüssel binary large Object (BLOB) enthalten sein soll.</span><span class="sxs-lookup"><span data-stu-id="5e176-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="5e176-111">[in] Ein Zeiger auf das öffentlich/privat-Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="5e176-111">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="5e176-112">Dieses Paar hat das Format, das erstellt wird, durch die Win32- `CryptExportKey` Funktion.</span><span class="sxs-lookup"><span data-stu-id="5e176-112">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="5e176-113">Wenn `pbKeyBlob` null festgelegt ist, die mit angegebenen Container `wszKeyContainer` wird davon ausgegangen, dass das Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="5e176-113">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="5e176-114">[in] Die Größe in Bytes, des `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="5e176-114">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="5e176-115">[out] Ein Zeiger auf den Speicherort, an dem die common Language Runtime die Signatur zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="5e176-115">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="5e176-116">Wenn `ppbSignatureBlob` ist null, die Laufzeit speichert-die Signatur in der Datei, die anhand des `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="5e176-116">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="5e176-117">Wenn `ppbSignatureBlob` ist nicht null ist, belegt die common Language Runtime Speicherplatz in dem die Signatur zurück.</span><span class="sxs-lookup"><span data-stu-id="5e176-117">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="5e176-118">Der Aufrufer muss diesen Speicherplatz mit Freigeben der [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="5e176-118">The caller must free this space using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="5e176-119">[out] Die Größe in Bytes der zurückgegebenen Signatur.</span><span class="sxs-lookup"><span data-stu-id="5e176-119">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="5e176-120">[in] Eine oder mehrere der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="5e176-120">[in] One or more of the following values:</span></span>  
  
-   <span data-ttu-id="5e176-121">`SN_SIGN_ALL_FILES` (0 x 00000001) – alle Hashes für verknüpfte Module neu.</span><span class="sxs-lookup"><span data-stu-id="5e176-121">`SN_SIGN_ALL_FILES` (0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
-   <span data-ttu-id="5e176-122">`SN_TEST_SIGN` (0 x 00000002) - Test Signierung der Assembly.</span><span class="sxs-lookup"><span data-stu-id="5e176-122">`SN_TEST_SIGN` (0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5e176-123">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5e176-123">Return Value</span></span>  
 <span data-ttu-id="5e176-124">`S_OK` Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="5e176-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e176-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5e176-125">Remarks</span></span>  
 <span data-ttu-id="5e176-126">Geben Sie null für `wszFilePath` um die Größe der Signatur zu berechnen, ohne die Signatur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5e176-126">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="5e176-127">Die Signatur kann werden entweder direkt in der Datei gespeichert oder an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5e176-127">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="5e176-128">Wenn `SN_SIGN_ALL_FILES` angegeben ist, aber ein öffentlicher Schlüssel nicht enthalten ist. (beide `pbKeyBlob` und `wszFilePath` null sind), werden Hashes für verknüpfte Module neu berechnet, aber die Assembly wird nicht erneut signiert.</span><span class="sxs-lookup"><span data-stu-id="5e176-128">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="5e176-129">Wenn `SN_TEST_SIGN` angegeben ist, wird die common Language Runtime-Header wird nicht geändert, um anzugeben, dass die Assembly mit einem starken Namen signiert ist.</span><span class="sxs-lookup"><span data-stu-id="5e176-129">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e176-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5e176-130">Requirements</span></span>  
 <span data-ttu-id="5e176-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e176-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e176-132">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="5e176-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5e176-133">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5e176-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5e176-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e176-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e176-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e176-135">See Also</span></span>  
 [<span data-ttu-id="5e176-136">StrongNameSignatureGeneration-Methode</span><span class="sxs-lookup"><span data-stu-id="5e176-136">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)  
 [<span data-ttu-id="5e176-137">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e176-137">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
