---
title: StrongNameGetPublicKeyEx-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName2.StrongNameGetPublicKeyEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameGetPublicKeyEx
helpviewer_keywords:
- StrongNameGetPublicKeyEx method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameGetPublicKeyEx method [.NET Framework hosting]
ms.assetid: 63d8260c-fb32-4f8f-a357-768afd570f68
topic_type:
- apiref
ms.openlocfilehash: 93afe1afd9ea9637d039a8b4a4e81267d49c08b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176226"
---
# <a name="strongnamegetpublickeyex-method"></a><span data-ttu-id="77da9-102">StrongNameGetPublicKeyEx-Methode</span><span class="sxs-lookup"><span data-stu-id="77da9-102">StrongNameGetPublicKeyEx Method</span></span>
<span data-ttu-id="77da9-103">Ruft den öffentlichen Schlüssel von einem öffentlichen/privaten Schlüsselpaar ab und gibt einen Hashalgorithmus und einen Signaturalgorithmus an.</span><span class="sxs-lookup"><span data-stu-id="77da9-103">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77da9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="77da9-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetPublicKey (
    [in]  LPCWSTR   pwzKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
    [in]  ULONG     uHashAlgId,  
    [in]  ULONG     uReserved,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77da9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="77da9-105">Parameters</span></span>  
 `pwzKeyContainer`  
 <span data-ttu-id="77da9-106">[in] Der Name des Schlüsselcontainers, der das öffentliche/private Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="77da9-106">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="77da9-107">Wenn `pbKeyBlob` null `szKeyContainer` ist, muss ein gültiger Container innerhalb des Kryptografiedienstanbieters (Cryptographic Service Provider, CSP) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="77da9-107">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="77da9-108">In diesem Fall `StrongNameGetPublicKeyEx` extrahiert die Methode den öffentlichen Schlüssel aus dem im Container gespeicherten Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="77da9-108">In this case, the `StrongNameGetPublicKeyEx` method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="77da9-109">Wenn `pbKeyBlob` es nicht null ist, wird davon ausgegangen, dass das Schlüsselpaar im PpbLOB (Key Binary Large Object) enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="77da9-109">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="77da9-110">Die Schlüssel müssen 1024-Bit Rivest-Shamir-Adleman (RSA) Signaturschlüssel sein.</span><span class="sxs-lookup"><span data-stu-id="77da9-110">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="77da9-111">Derzeit werden keine anderen Schlüsseltypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="77da9-111">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="77da9-112">[in] Ein Zeiger auf das öffentliche/private Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="77da9-112">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="77da9-113">Dieses Paar hat das Format, das `CryptExportKey` von der Win32-Funktion erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="77da9-113">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="77da9-114">Wenn `pbKeyBlob` null ist, wird `szKeyContainer` davon ausgegangen, dass der von festgelegte Schlüsselcontainer das Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="77da9-114">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="77da9-115">[in] Die Größe von in `pbKeyBlob`Bytes von .</span><span class="sxs-lookup"><span data-stu-id="77da9-115">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="77da9-116">[out] Der zurückgegebene BLOB des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="77da9-116">[out] The returned public key BLOB.</span></span> <span data-ttu-id="77da9-117">Der `ppbPublicKeyBlob` Parameter wird von der Common Language Runtime zugewiesen und an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="77da9-117">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="77da9-118">Der Aufrufer muss den Speicher mithilfe der [ICLRStrongName::StrongNameFreeBuffer-Methode freigeben.](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)</span><span class="sxs-lookup"><span data-stu-id="77da9-118">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="77da9-119">[out] Die Größe des zurückgegebenen bLOB für den öffentlichen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="77da9-119">[out] The size of the returned public key BLOB.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="77da9-120">[in] Der Assemblyhashalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="77da9-120">[in] The assembly hash algorithm.</span></span> <span data-ttu-id="77da9-121">Eine Liste der akzeptierten Werte finden Sie im Abschnitt "Bemerkungen".</span><span class="sxs-lookup"><span data-stu-id="77da9-121">See the Remarks section for a list of accepted values.</span></span>  
  
 `uReserved`  
 <span data-ttu-id="77da9-122">[in] Reserviert für die zukünftige Verwendung; Standardwert auf null.</span><span class="sxs-lookup"><span data-stu-id="77da9-122">[in] Reserved for future use; defaults to null.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="77da9-123">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="77da9-123">Return Value</span></span>  
 <span data-ttu-id="77da9-124">`S_OK`wenn die Methode erfolgreich abgeschlossen wurde; Andernfalls ein HRESULT-Wert, der auf einen Fehler hinweist (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="77da9-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77da9-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="77da9-125">Remarks</span></span>  
 <span data-ttu-id="77da9-126">Der öffentliche Schlüssel ist in einer [PublicKeyBlob-Struktur](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) enthalten.</span><span class="sxs-lookup"><span data-stu-id="77da9-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77da9-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="77da9-127">Remarks</span></span>  
 <span data-ttu-id="77da9-128">Die folgende Tabelle zeigt den Satz `uHashAlgId` der akzeptierten Werte für den Parameter.</span><span class="sxs-lookup"><span data-stu-id="77da9-128">The following table shows the set of accepted values for the `uHashAlgId` parameter.</span></span>  
  
|<span data-ttu-id="77da9-129">Name</span><span class="sxs-lookup"><span data-stu-id="77da9-129">Name</span></span>|<span data-ttu-id="77da9-130">value</span><span class="sxs-lookup"><span data-stu-id="77da9-130">Value</span></span>|  
|----------|-----------|  
|<span data-ttu-id="77da9-131">Keine</span><span class="sxs-lookup"><span data-stu-id="77da9-131">None</span></span>|<span data-ttu-id="77da9-132">0</span><span class="sxs-lookup"><span data-stu-id="77da9-132">0</span></span>|  
|<span data-ttu-id="77da9-133">SHA-1</span><span class="sxs-lookup"><span data-stu-id="77da9-133">SHA-1</span></span>|<span data-ttu-id="77da9-134">0x8004</span><span class="sxs-lookup"><span data-stu-id="77da9-134">0x8004</span></span>|  
|<span data-ttu-id="77da9-135">SHA-256</span><span class="sxs-lookup"><span data-stu-id="77da9-135">SHA-256</span></span>|<span data-ttu-id="77da9-136">0x800c</span><span class="sxs-lookup"><span data-stu-id="77da9-136">0x800c</span></span>|  
|<span data-ttu-id="77da9-137">SHA-384</span><span class="sxs-lookup"><span data-stu-id="77da9-137">SHA-384</span></span>|<span data-ttu-id="77da9-138">0x800d</span><span class="sxs-lookup"><span data-stu-id="77da9-138">0x800d</span></span>|  
|<span data-ttu-id="77da9-139">SHA-512</span><span class="sxs-lookup"><span data-stu-id="77da9-139">SHA-512</span></span>|<span data-ttu-id="77da9-140">0x800e</span><span class="sxs-lookup"><span data-stu-id="77da9-140">0x800e</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="77da9-141">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="77da9-141">Requirements</span></span>  
 <span data-ttu-id="77da9-142">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77da9-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77da9-143">**Kopfzeile:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="77da9-143">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="77da9-144">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="77da9-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="77da9-145">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77da9-145">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77da9-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="77da9-146">See also</span></span>

- [<span data-ttu-id="77da9-147">StrongNameTokenFromPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="77da9-147">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="77da9-148">PublicKeyBlob-Struktur</span><span class="sxs-lookup"><span data-stu-id="77da9-148">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="77da9-149">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="77da9-149">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="77da9-150">StrongNameGetPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="77da9-150">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
