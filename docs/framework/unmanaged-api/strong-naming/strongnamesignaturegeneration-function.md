---
title: StrongNameSignatureGeneration-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGeneration
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration function [.NET Framework strong naming]
ms.assetid: 839b765c-3e41-44ce-bf1b-dc10453db18e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a33c2240a0e3f3a09ff5ce93c34db9bba03ab83
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54665070"
---
# <a name="strongnamesignaturegeneration-function"></a><span data-ttu-id="0d60d-102">StrongNameSignatureGeneration-Funktion</span><span class="sxs-lookup"><span data-stu-id="0d60d-102">StrongNameSignatureGeneration Function</span></span>
<span data-ttu-id="0d60d-103">Generiert eine Signatur mit starkem Namen für die angegebene Assembly.</span><span class="sxs-lookup"><span data-stu-id="0d60d-103">Generates a strong name signature for the specified assembly.</span></span>  
  
 <span data-ttu-id="0d60d-104">Diese Funktion wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="0d60d-104">This function has been deprecated.</span></span> <span data-ttu-id="0d60d-105">Verwenden der [ICLRStrongName:: StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="0d60d-105">Use the [ICLRStrongName::StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d60d-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="0d60d-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureGeneration (   
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0d60d-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="0d60d-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="0d60d-108">[in] Der Pfad zur Datei, die das Manifest der Assembly enthält, für die Signatur mit starkem Namen generiert wird.</span><span class="sxs-lookup"><span data-stu-id="0d60d-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="0d60d-109">[in] Der Name des Schlüsselcontainers, die das öffentlich/privat-Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="0d60d-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="0d60d-110">Wenn `pbKeyBlob` null ist, `wszKeyContainer` müssen einen gültigen Container innerhalb der Kryptografiedienstanbieter (CSP) angeben.</span><span class="sxs-lookup"><span data-stu-id="0d60d-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="0d60d-111">In diesem Fall dient das Schlüsselpaar im Container gespeicherten zum Signieren der Datei.</span><span class="sxs-lookup"><span data-stu-id="0d60d-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="0d60d-112">Wenn `pbKeyBlob` ist nicht null ist, das Schlüsselpaar wird davon ausgegangen, dass im Schlüssel binary large Object (BLOB) enthalten sein soll.</span><span class="sxs-lookup"><span data-stu-id="0d60d-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="0d60d-113">Die Schlüssel müssen 1024-Bit-Rivest-Shamir-Adleman (RSA) Signaturschlüssel sein.</span><span class="sxs-lookup"><span data-stu-id="0d60d-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="0d60d-114">Es werden keine anderen Arten von Schlüsseln zu diesem Zeitpunkt unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0d60d-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="0d60d-115">[in] Ein Zeiger auf das öffentlich/privat-Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="0d60d-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="0d60d-116">Dieses Paar hat das Format, das erstellt wird, durch die Win32- `CryptExportKey` Funktion.</span><span class="sxs-lookup"><span data-stu-id="0d60d-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="0d60d-117">Wenn `pbKeyBlob` null festgelegt ist, die mit angegebenen Container `wszKeyContainer` wird davon ausgegangen, dass das Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="0d60d-117">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="0d60d-118">[in] Die Größe in Bytes, des `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="0d60d-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="0d60d-119">[out] Ein Zeiger auf den Speicherort, an dem die common Language Runtime die Signatur zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="0d60d-119">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="0d60d-120">Wenn `ppbSignatureBlob` ist null, die Laufzeit speichert-die Signatur in der Datei, die anhand des `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="0d60d-120">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="0d60d-121">Wenn `ppbSignatureBlob` ist nicht null ist, belegt die common Language Runtime Speicherplatz in dem die Signatur zurück.</span><span class="sxs-lookup"><span data-stu-id="0d60d-121">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="0d60d-122">Der Aufrufer muss diesen Speicherplatz mit Freigeben der [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="0d60d-122">The caller must free this space using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="0d60d-123">[out] Die Größe in Bytes der zurückgegebenen Signatur.</span><span class="sxs-lookup"><span data-stu-id="0d60d-123">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d60d-124">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0d60d-124">Return Value</span></span>  
 <span data-ttu-id="0d60d-125">`true` Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="0d60d-125">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d60d-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0d60d-126">Remarks</span></span>  
 <span data-ttu-id="0d60d-127">Geben Sie null für `wszFilePath` um die Größe der Signatur zu berechnen, ohne die Signatur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0d60d-127">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="0d60d-128">Die Signatur kann entweder direkt in der Datei gespeichert oder an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0d60d-128">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="0d60d-129">Wenn die `StrongNameSignatureGeneration` Funktion nicht erfolgreich abgeschlossen wurde, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0d60d-129">If the `StrongNameSignatureGeneration` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d60d-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0d60d-130">Requirements</span></span>  
 <span data-ttu-id="0d60d-131">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d60d-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d60d-132">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="0d60d-132">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="0d60d-133">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0d60d-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0d60d-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d60d-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d60d-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0d60d-135">See also</span></span>
- [<span data-ttu-id="0d60d-136">StrongNameSignatureGeneration-Methode</span><span class="sxs-lookup"><span data-stu-id="0d60d-136">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="0d60d-137">StrongNameSignatureGenerationEx-Methode</span><span class="sxs-lookup"><span data-stu-id="0d60d-137">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="0d60d-138">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0d60d-138">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
