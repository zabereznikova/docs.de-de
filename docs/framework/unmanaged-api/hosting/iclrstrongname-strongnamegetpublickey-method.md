---
title: ICLRStrongName::StrongNameGetPublicKey-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetPublicKey method [.NET Framework hosting]
ms.assetid: a31dcaa9-a404-4c1d-8cc7-081827c52935
topic_type:
- apiref
ms.openlocfilehash: cb96c7e17627205db0573e56fc8c2a29e7717434
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181934"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a><span data-ttu-id="d08a0-102">ICLRStrongName::StrongNameGetPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="d08a0-102">ICLRStrongName::StrongNameGetPublicKey Method</span></span>
<span data-ttu-id="d08a0-103">Ruft den öffentlichen Schlüssel von einem öffentlichen/privaten Schlüsselpaar ab.</span><span class="sxs-lookup"><span data-stu-id="d08a0-103">Gets the public key from a public/private key pair.</span></span> <span data-ttu-id="d08a0-104">Das Schlüsselpaar kann entweder als Schlüsselcontainername innerhalb eines Kryptografiedienstanbieters (Cryptographic Service Provider, CSP) oder als unformatierte Auflistung von Bytes angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d08a0-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d08a0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d08a0-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d08a0-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d08a0-106">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="d08a0-107">[in] Der Name des Schlüsselcontainers, der das öffentliche/private Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="d08a0-107">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="d08a0-108">Wenn `pbKeyBlob` null `szKeyContainer` ist, muss ein gültiger Container innerhalb des CSP angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d08a0-108">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="d08a0-109">In diesem Fall extrahiert die [ICLRStrongName::StrongNameGetPublicKey-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) den öffentlichen Schlüssel aus dem im Container gespeicherten Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="d08a0-109">In this case, the [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="d08a0-110">Wenn `pbKeyBlob` es nicht null ist, wird davon ausgegangen, dass das Schlüsselpaar im PpbLOB (Key Binary Large Object) enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="d08a0-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="d08a0-111">Die Schlüssel müssen 1024-Bit Rivest-Shamir-Adleman (RSA) Signaturschlüssel sein.</span><span class="sxs-lookup"><span data-stu-id="d08a0-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="d08a0-112">Derzeit werden keine anderen Schlüsseltypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d08a0-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="d08a0-113">[in] Ein Zeiger auf das öffentliche/private Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="d08a0-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="d08a0-114">Dieses Paar hat das Format, das `CryptExportKey` von der Win32-Funktion erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="d08a0-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="d08a0-115">Wenn `pbKeyBlob` null ist, wird `szKeyContainer` davon ausgegangen, dass der von festgelegte Schlüsselcontainer das Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="d08a0-115">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="d08a0-116">[in] Die Größe von in `pbKeyBlob`Bytes von .</span><span class="sxs-lookup"><span data-stu-id="d08a0-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="d08a0-117">[out] Der zurückgegebene BLOB des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="d08a0-117">[out] The returned public key BLOB.</span></span> <span data-ttu-id="d08a0-118">Der `ppbPublicKeyBlob` Parameter wird von der Common Language Runtime zugewiesen und an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d08a0-118">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="d08a0-119">Der Aufrufer muss den Speicher mithilfe der [ICLRStrongName::StrongNameFreeBuffer-Methode freigeben.](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)</span><span class="sxs-lookup"><span data-stu-id="d08a0-119">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="d08a0-120">[out] Die Größe des zurückgegebenen bLOB für den öffentlichen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="d08a0-120">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d08a0-121">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d08a0-121">Return Value</span></span>  
 <span data-ttu-id="d08a0-122">`S_OK`wenn die Methode erfolgreich abgeschlossen wurde; Andernfalls ein HRESULT-Wert, der auf einen Fehler hinweist (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="d08a0-122">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d08a0-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d08a0-123">Remarks</span></span>  
 <span data-ttu-id="d08a0-124">Der öffentliche Schlüssel ist in einer [PublicKeyBlob-Struktur](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) enthalten.</span><span class="sxs-lookup"><span data-stu-id="d08a0-124">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d08a0-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d08a0-125">Requirements</span></span>  
 <span data-ttu-id="d08a0-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d08a0-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d08a0-127">**Kopfzeile:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="d08a0-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d08a0-128">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d08a0-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d08a0-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d08a0-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d08a0-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d08a0-130">See also</span></span>

- [<span data-ttu-id="d08a0-131">StrongNameTokenFromPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="d08a0-131">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="d08a0-132">PublicKeyBlob-Struktur</span><span class="sxs-lookup"><span data-stu-id="d08a0-132">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="d08a0-133">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d08a0-133">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
