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
ms.openlocfilehash: ced7540afe931fb91240c770d76d205400157a51
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901106"
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a><span data-ttu-id="fadac-102">ICLRStrongName::StrongNameSignatureGeneration-Methode</span><span class="sxs-lookup"><span data-stu-id="fadac-102">ICLRStrongName::StrongNameSignatureGeneration Method</span></span>
<span data-ttu-id="fadac-103">Generiert eine Signatur mit starkem Namen für die angegebene Assembly.</span><span class="sxs-lookup"><span data-stu-id="fadac-103">Generates a strong name signature for the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fadac-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fadac-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="fadac-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="fadac-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="fadac-106">in Der Pfad zu der Datei, die das Manifest der Assembly enthält, für die die starke namens Signatur generiert wird.</span><span class="sxs-lookup"><span data-stu-id="fadac-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="fadac-107">in Der Name des Schlüssel Containers, der das Paar aus öffentlichem und privatem Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="fadac-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="fadac-108">Wenn `pbKeyBlob` NULL ist, muss `wszKeyContainer` einen gültigen Container innerhalb des Kryptografiedienstanbieters (kryptografischen Service Provider, CSP) angeben.</span><span class="sxs-lookup"><span data-stu-id="fadac-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="fadac-109">In diesem Fall wird das im Container gespeicherte Schlüsselpaar zum Signieren der Datei verwendet.</span><span class="sxs-lookup"><span data-stu-id="fadac-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="fadac-110">Wenn `pbKeyBlob` nicht NULL ist, wird angenommen, dass das Schlüsselpaar im Schlüssel Binary Large Object (BLOB) enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="fadac-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="fadac-111">Die Schlüssel müssen 1024-Bit-Rivest-Shamir-Adleman (RSA)-Signatur Schlüssel sein.</span><span class="sxs-lookup"><span data-stu-id="fadac-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="fadac-112">Zurzeit werden keine anderen Schlüsseltypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fadac-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="fadac-113">in Ein Zeiger auf das Paar aus öffentlichem und privatem Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="fadac-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="fadac-114">Dieses Paar weist das Format auf, das von der Win32-`CryptExportKey`-Funktion erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="fadac-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="fadac-115">Wenn `pbKeyBlob` NULL ist, wird angenommen, dass der von `wszKeyContainer` angegebene Schlüssel Container das Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="fadac-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="fadac-116">in Die Größe `pbKeyBlob`in Byte.</span><span class="sxs-lookup"><span data-stu-id="fadac-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="fadac-117">vorgenommen Ein Zeiger auf den Speicherort, an den der Common Language Runtime die Signatur zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="fadac-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="fadac-118">Wenn `ppbSignatureBlob` NULL ist, speichert die Laufzeit die Signatur in der durch `wszFilePath`angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="fadac-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="fadac-119">Wenn `ppbSignatureBlob` nicht NULL ist, ordnet die Common Language Runtime Speicherplatz zu, in dem die Signatur zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="fadac-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="fadac-120">Der Aufrufer muss diesen Bereich mithilfe der [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) -Methode freigeben.</span><span class="sxs-lookup"><span data-stu-id="fadac-120">The caller must free this space by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="fadac-121">vorgenommen Die Größe (in Bytes) der zurückgegebenen Signatur.</span><span class="sxs-lookup"><span data-stu-id="fadac-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fadac-122">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fadac-122">Return Value</span></span>  
 <span data-ttu-id="fadac-123">`S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="fadac-123">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fadac-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fadac-124">Remarks</span></span>  
 <span data-ttu-id="fadac-125">Geben Sie NULL für `wszFilePath` an, um die Größe der Signatur zu berechnen, ohne die Signatur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fadac-125">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="fadac-126">Die Signatur kann entweder direkt in der Datei gespeichert oder an den Aufrufer zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fadac-126">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fadac-127">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fadac-127">Requirements</span></span>  
 <span data-ttu-id="fadac-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fadac-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fadac-129">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="fadac-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fadac-130">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fadac-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fadac-131">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fadac-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fadac-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fadac-132">See also</span></span>

- [<span data-ttu-id="fadac-133">StrongNameSignatureGenerationEx-Methode</span><span class="sxs-lookup"><span data-stu-id="fadac-133">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="fadac-134">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fadac-134">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
