---
title: StrongNameSignatureGenerationEx-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGenerationEx
helpviewer_keywords:
- StrongNameSignatureGenerationEx function [.NET Framework strong naming]
ms.assetid: 9a75469e-aa49-4e32-ad48-3bafd5202f09
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5d60b9a9ae566b5bd686b27b2e09861a8414979
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190014"
---
# <a name="strongnamesignaturegenerationex-function"></a><span data-ttu-id="d2267-102">StrongNameSignatureGenerationEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="d2267-102">StrongNameSignatureGenerationEx Function</span></span>
<span data-ttu-id="d2267-103">Generiert eine Signatur mit starkem Namen für die angegebene Assembly gemäß den angegebenen Flags.</span><span class="sxs-lookup"><span data-stu-id="d2267-103">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
 <span data-ttu-id="d2267-104">Diese Funktion wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="d2267-104">This function has been deprecated.</span></span> <span data-ttu-id="d2267-105">Verwenden der [ICLRStrongName:: StrongNameSignatureGenerationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="d2267-105">Use the [ICLRStrongName::StrongNameSignatureGenerationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2267-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2267-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2267-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="d2267-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="d2267-108">[in] Der Pfad zur Datei, die das Manifest der Assembly enthält, für die Signatur mit starkem Namen generiert wird.</span><span class="sxs-lookup"><span data-stu-id="d2267-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="d2267-109">[in] Der Name des Schlüsselcontainers, die das öffentlich/privat-Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="d2267-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="d2267-110">Wenn `pbKeyBlob` null ist, `wszKeyContainer` müssen einen gültigen Container innerhalb der Kryptografiedienstanbieter (CSP) angeben.</span><span class="sxs-lookup"><span data-stu-id="d2267-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="d2267-111">In diesem Fall dient das Schlüsselpaar im Container gespeicherten zum Signieren der Datei.</span><span class="sxs-lookup"><span data-stu-id="d2267-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="d2267-112">Wenn `pbKeyBlob` ist nicht null ist, das Schlüsselpaar wird davon ausgegangen, dass im Schlüssel binary large Object (BLOB) enthalten sein soll.</span><span class="sxs-lookup"><span data-stu-id="d2267-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="d2267-113">[in] Ein Zeiger auf das öffentlich/privat-Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="d2267-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="d2267-114">Dieses Paar hat das Format, das erstellt wird, durch die Win32- `CryptExportKey` Funktion.</span><span class="sxs-lookup"><span data-stu-id="d2267-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="d2267-115">Wenn `pbKeyBlob` null festgelegt ist, die mit angegebenen Container `wszKeyContainer` wird davon ausgegangen, dass das Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="d2267-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="d2267-116">[in] Die Größe in Bytes, des `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="d2267-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="d2267-117">[out] Ein Zeiger auf den Speicherort, an dem die common Language Runtime die Signatur zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d2267-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="d2267-118">Wenn `ppbSignatureBlob` ist null, die Laufzeit speichert-die Signatur in der Datei, die anhand des `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="d2267-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="d2267-119">Wenn `ppbSignatureBlob` ist nicht null ist, belegt die common Language Runtime Speicherplatz in dem die Signatur zurück.</span><span class="sxs-lookup"><span data-stu-id="d2267-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="d2267-120">Der Aufrufer muss diesen Speicherplatz mit Freigeben der [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="d2267-120">The caller must free this space using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="d2267-121">[out] Die Größe in Bytes der zurückgegebenen Signatur.</span><span class="sxs-lookup"><span data-stu-id="d2267-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d2267-122">[in] Eine oder mehrere der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="d2267-122">[in] One or more of the following values:</span></span>  
  
-   `SN_SIGN_ALL_FILES` <span data-ttu-id="d2267-123">(0 x 00000001) – alle Hashes für verknüpfte Module neu.</span><span class="sxs-lookup"><span data-stu-id="d2267-123">(0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
-   `SN_TEST_SIGN` <span data-ttu-id="d2267-124">(0 x 00000002) - Test Signierung der Assembly.</span><span class="sxs-lookup"><span data-stu-id="d2267-124">(0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2267-125">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d2267-125">Return Value</span></span>  
 `true` <span data-ttu-id="d2267-126">Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="d2267-126">on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2267-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d2267-127">Remarks</span></span>  
 <span data-ttu-id="d2267-128">Geben Sie null für `wszFilePath` um die Größe der Signatur zu berechnen, ohne die Signatur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d2267-128">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="d2267-129">Die Signatur kann werden entweder direkt in der Datei gespeichert oder an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d2267-129">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="d2267-130">Wenn `SN_SIGN_ALL_FILES` angegeben ist, aber ein öffentlicher Schlüssel nicht enthalten ist. (beide `pbKeyBlob` und `wszFilePath` null sind), werden Hashes für verknüpfte Module neu berechnet, aber die Assembly wird nicht erneut signiert.</span><span class="sxs-lookup"><span data-stu-id="d2267-130">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="d2267-131">Wenn `SN_TEST_SIGN` angegeben ist, wird die common Language Runtime-Header wird nicht geändert, um anzugeben, dass die Assembly mit einem starken Namen signiert ist.</span><span class="sxs-lookup"><span data-stu-id="d2267-131">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
 <span data-ttu-id="d2267-132">Wenn die `StrongNameSignatureGenerationEx` Funktion nicht erfolgreich abgeschlossen wurde, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d2267-132">If the `StrongNameSignatureGenerationEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2267-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d2267-133">Requirements</span></span>  
 <span data-ttu-id="d2267-134">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2267-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2267-135">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="d2267-135">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d2267-136">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d2267-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="d2267-137">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="d2267-137">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d2267-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2267-138">See also</span></span>

- [<span data-ttu-id="d2267-139">StrongNameSignatureGenerationEx-Methode</span><span class="sxs-lookup"><span data-stu-id="d2267-139">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="d2267-140">StrongNameSignatureGeneration-Methode</span><span class="sxs-lookup"><span data-stu-id="d2267-140">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="d2267-141">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d2267-141">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
