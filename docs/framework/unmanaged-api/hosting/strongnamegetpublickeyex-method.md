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
ms.openlocfilehash: 1904a98f254a988ce035847a4cdeede182aa07bf
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006374"
---
# <a name="strongnamegetpublickeyex-method"></a><span data-ttu-id="0b3cf-102">StrongNameGetPublicKeyEx-Methode</span><span class="sxs-lookup"><span data-stu-id="0b3cf-102">StrongNameGetPublicKeyEx Method</span></span>
<span data-ttu-id="0b3cf-103">Ruft den öffentlichen Schlüssel aus einem Paar aus öffentlichem und privatem Schlüssel ab und gibt einen Hash Algorithmus und einen Signatur Algorithmus an.</span><span class="sxs-lookup"><span data-stu-id="0b3cf-103">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b3cf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b3cf-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="0b3cf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0b3cf-105">Parameters</span></span>  
 `pwzKeyContainer`  
 <span data-ttu-id="0b3cf-106">in Der Name des Schlüssel Containers, der das Paar aus öffentlichem und privatem Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="0b3cf-106">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="0b3cf-107">Wenn `pbKeyBlob` NULL ist, `szKeyContainer` muss einen gültigen Container innerhalb des Kryptografiedienstanbieters (kryptografischen Service Provider, CSP) angeben.</span><span class="sxs-lookup"><span data-stu-id="0b3cf-107">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="0b3cf-108">In diesem Fall extrahiert die- `StrongNameGetPublicKeyEx` Methode den öffentlichen Schlüssel aus dem Schlüsselpaar, das im Container gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="0b3cf-108">In this case, the `StrongNameGetPublicKeyEx` method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="0b3cf-109">Wenn `pbKeyBlob` nicht NULL ist, wird angenommen, dass das Schlüsselpaar im Schlüssel Binary Large Object (BLOB) enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="0b3cf-109">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="0b3cf-110">Die Schlüssel müssen 1024-Bit-Rivest-Shamir-Adleman (RSA)-Signatur Schlüssel sein.</span><span class="sxs-lookup"><span data-stu-id="0b3cf-110">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="0b3cf-111">Zurzeit werden keine anderen Schlüsseltypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0b3cf-111">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="0b3cf-112">in Ein Zeiger auf das Paar aus öffentlichem und privatem Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="0b3cf-112">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="0b3cf-113">Dieses Paar weist das Format auf, das von der Win32-Funktion erstellt wird `CryptExportKey` .</span><span class="sxs-lookup"><span data-stu-id="0b3cf-113">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="0b3cf-114">Wenn `pbKeyBlob` NULL ist, wird angenommen, dass der von angegebene Schlüssel Container `szKeyContainer` das Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="0b3cf-114">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="0b3cf-115">in Die Größe von in Bytes `pbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="0b3cf-115">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="0b3cf-116">vorgenommen Das zurückgegebene BLOB für öffentliche Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="0b3cf-116">[out] The returned public key BLOB.</span></span> <span data-ttu-id="0b3cf-117">Der `ppbPublicKeyBlob` -Parameter wird vom Common Language Runtime zugeordnet und an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0b3cf-117">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="0b3cf-118">Der Aufrufer muss den Speicher mithilfe der [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) -Methode freigeben.</span><span class="sxs-lookup"><span data-stu-id="0b3cf-118">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="0b3cf-119">vorgenommen Die Größe des zurückgegebenen BLOBs für öffentliche Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="0b3cf-119">[out] The size of the returned public key BLOB.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="0b3cf-120">in Der Assembly-Hash Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="0b3cf-120">[in] The assembly hash algorithm.</span></span> <span data-ttu-id="0b3cf-121">Eine Liste der akzeptierten Werte finden Sie im Abschnitt "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="0b3cf-121">See the Remarks section for a list of accepted values.</span></span>  
  
 `uReserved`  
 <span data-ttu-id="0b3cf-122">in Für zukünftige Verwendung reserviert. der Standardwert ist NULL.</span><span class="sxs-lookup"><span data-stu-id="0b3cf-122">[in] Reserved for future use; defaults to null.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b3cf-123">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0b3cf-123">Return Value</span></span>  
 <span data-ttu-id="0b3cf-124">`S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="0b3cf-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b3cf-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0b3cf-125">Remarks</span></span>  
 <span data-ttu-id="0b3cf-126">Der öffentliche Schlüssel ist in einer [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) -Struktur enthalten.</span><span class="sxs-lookup"><span data-stu-id="0b3cf-126">The public key is contained in a [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b3cf-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0b3cf-127">Remarks</span></span>  
 <span data-ttu-id="0b3cf-128">In der folgenden Tabelle sind die zulässigen Werte für den- `uHashAlgId` Parameter aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="0b3cf-128">The following table shows the set of accepted values for the `uHashAlgId` parameter.</span></span>  
  
|<span data-ttu-id="0b3cf-129">Name</span><span class="sxs-lookup"><span data-stu-id="0b3cf-129">Name</span></span>|<span data-ttu-id="0b3cf-130">Wert</span><span class="sxs-lookup"><span data-stu-id="0b3cf-130">Value</span></span>|  
|----------|-----------|  
|<span data-ttu-id="0b3cf-131">Keine</span><span class="sxs-lookup"><span data-stu-id="0b3cf-131">None</span></span>|<span data-ttu-id="0b3cf-132">0</span><span class="sxs-lookup"><span data-stu-id="0b3cf-132">0</span></span>|  
|<span data-ttu-id="0b3cf-133">SHA-1</span><span class="sxs-lookup"><span data-stu-id="0b3cf-133">SHA-1</span></span>|<span data-ttu-id="0b3cf-134">0x8004</span><span class="sxs-lookup"><span data-stu-id="0b3cf-134">0x8004</span></span>|  
|<span data-ttu-id="0b3cf-135">SHA-256</span><span class="sxs-lookup"><span data-stu-id="0b3cf-135">SHA-256</span></span>|<span data-ttu-id="0b3cf-136">0x800c</span><span class="sxs-lookup"><span data-stu-id="0b3cf-136">0x800c</span></span>|  
|<span data-ttu-id="0b3cf-137">SHA-384</span><span class="sxs-lookup"><span data-stu-id="0b3cf-137">SHA-384</span></span>|<span data-ttu-id="0b3cf-138">0x800d</span><span class="sxs-lookup"><span data-stu-id="0b3cf-138">0x800d</span></span>|  
|<span data-ttu-id="0b3cf-139">SHA-512</span><span class="sxs-lookup"><span data-stu-id="0b3cf-139">SHA-512</span></span>|<span data-ttu-id="0b3cf-140">0x800e</span><span class="sxs-lookup"><span data-stu-id="0b3cf-140">0x800e</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0b3cf-141">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0b3cf-141">Requirements</span></span>  
 <span data-ttu-id="0b3cf-142">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b3cf-142">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b3cf-143">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="0b3cf-143">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0b3cf-144">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0b3cf-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0b3cf-145">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b3cf-145">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b3cf-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b3cf-146">See also</span></span>

- [<span data-ttu-id="0b3cf-147">StrongNameTokenFromPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="0b3cf-147">StrongNameTokenFromPublicKey Method</span></span>](iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="0b3cf-148">PublicKeyBlob-Struktur</span><span class="sxs-lookup"><span data-stu-id="0b3cf-148">PublicKeyBlob Structure</span></span>](../strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="0b3cf-149">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0b3cf-149">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
- [<span data-ttu-id="0b3cf-150">StrongNameGetPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="0b3cf-150">StrongNameGetPublicKey Method</span></span>](iclrstrongname-strongnamegetpublickey-method.md)
