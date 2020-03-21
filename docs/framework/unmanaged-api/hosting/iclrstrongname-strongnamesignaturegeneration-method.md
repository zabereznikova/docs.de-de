---
title: ICLRStrongName::StrongNameSignatureGeneration-Methode
ms.date: 03/30/2017
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
ms.openlocfilehash: e58ac181c4e472c469076b880ff71e0c6afa30fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178052"
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a><span data-ttu-id="541be-102">ICLRStrongName::StrongNameSignatureGeneration-Methode</span><span class="sxs-lookup"><span data-stu-id="541be-102">ICLRStrongName::StrongNameSignatureGeneration Method</span></span>
<span data-ttu-id="541be-103">Generiert eine Signatur mit starkem Namen für die angegebene Assembly.</span><span class="sxs-lookup"><span data-stu-id="541be-103">Generates a strong name signature for the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="541be-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="541be-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureGeneration (
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="541be-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="541be-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="541be-106">[in] Der Pfad zur Datei, die das Manifest der Assembly enthält, für die die Signatur mit starkem Namen generiert wird.</span><span class="sxs-lookup"><span data-stu-id="541be-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="541be-107">[in] Der Name des Schlüsselcontainers, der das öffentliche/private Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="541be-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="541be-108">Wenn `pbKeyBlob` null `wszKeyContainer` ist, muss ein gültiger Container innerhalb des Kryptografiedienstanbieters (Cryptographic Service Provider, CSP) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="541be-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="541be-109">In diesem Fall wird das im Container gespeicherte Schlüsselpaar zum Signieren der Datei verwendet.</span><span class="sxs-lookup"><span data-stu-id="541be-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="541be-110">Wenn `pbKeyBlob` es nicht null ist, wird davon ausgegangen, dass das Schlüsselpaar im PpbLOB (Key Binary Large Object) enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="541be-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="541be-111">Die Schlüssel müssen 1024-Bit Rivest-Shamir-Adleman (RSA) Signaturschlüssel sein.</span><span class="sxs-lookup"><span data-stu-id="541be-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="541be-112">Derzeit werden keine anderen Schlüsseltypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="541be-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="541be-113">[in] Ein Zeiger auf das öffentliche/private Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="541be-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="541be-114">Dieses Paar hat das Format, das `CryptExportKey` von der Win32-Funktion erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="541be-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="541be-115">Wenn `pbKeyBlob` null ist, wird `wszKeyContainer` davon ausgegangen, dass der von festgelegte Schlüsselcontainer das Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="541be-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="541be-116">[in] Die Größe von in `pbKeyBlob`Bytes von .</span><span class="sxs-lookup"><span data-stu-id="541be-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="541be-117">[out] Ein Zeiger auf den Speicherort, an den die Common Language Runtime die Signatur zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="541be-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="541be-118">Wenn `ppbSignatureBlob` null, speichert die Laufzeit die Signatur `wszFilePath`in der datei, die von angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="541be-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="541be-119">Wenn `ppbSignatureBlob` dies nicht null ist, weist die Common Language Runtime Speicherplatz zu, in dem die Signatur zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="541be-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="541be-120">Der Aufrufer muss diesen Speicherplatz mithilfe der [ICLRStrongName::StrongNameFreeBuffer-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) freizugeben.</span><span class="sxs-lookup"><span data-stu-id="541be-120">The caller must free this space by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="541be-121">[out] Die Größe der zurückgegebenen Signatur in Bytes.</span><span class="sxs-lookup"><span data-stu-id="541be-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="541be-122">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="541be-122">Return Value</span></span>  
 <span data-ttu-id="541be-123">`S_OK`wenn die Methode erfolgreich abgeschlossen wurde; Andernfalls ein HRESULT-Wert, der auf einen Fehler hinweist (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="541be-123">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="541be-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="541be-124">Remarks</span></span>  
 <span data-ttu-id="541be-125">Geben Sie `wszFilePath` NULL an, um die Größe der Signatur zu berechnen, ohne die Signatur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="541be-125">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="541be-126">Die Signatur kann entweder direkt in der Datei gespeichert oder an den Aufrufer zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="541be-126">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="541be-127">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="541be-127">Requirements</span></span>  
 <span data-ttu-id="541be-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="541be-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="541be-129">**Kopfzeile:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="541be-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="541be-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="541be-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="541be-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="541be-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="541be-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="541be-132">See also</span></span>

- [<span data-ttu-id="541be-133">StrongNameSignatureGenerationEx-Methode</span><span class="sxs-lookup"><span data-stu-id="541be-133">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="541be-134">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="541be-134">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
