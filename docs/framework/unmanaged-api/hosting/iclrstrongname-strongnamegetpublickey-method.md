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
ms.openlocfilehash: 5bd314b2b63474d2a1d159f74564e2d4ca13aef6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725546"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a><span data-ttu-id="6c746-102">ICLRStrongName::StrongNameGetPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="6c746-102">ICLRStrongName::StrongNameGetPublicKey Method</span></span>

<span data-ttu-id="6c746-103">Ruft den öffentlichen Schlüssel aus einem Paar aus öffentlichem und privatem Schlüssel ab.</span><span class="sxs-lookup"><span data-stu-id="6c746-103">Gets the public key from a public/private key pair.</span></span> <span data-ttu-id="6c746-104">Das Schlüsselpaar kann entweder als Schlüssel Container Name innerhalb eines Kryptografiedienstanbieters (kryptografischen Service Provider, CSP) oder als unformatierte Sammlung von Bytes angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6c746-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c746-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c746-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c746-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="6c746-106">Parameters</span></span>  

 `szKeyContainer`  
 <span data-ttu-id="6c746-107">in Der Name des Schlüssel Containers, der das Paar aus öffentlichem und privatem Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="6c746-107">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="6c746-108">Wenn `pbKeyBlob` NULL ist, `szKeyContainer` muss einen gültigen Container innerhalb des CSP angeben.</span><span class="sxs-lookup"><span data-stu-id="6c746-108">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="6c746-109">In diesem Fall extrahiert die [ICLRStrongName:: StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md) -Methode den öffentlichen Schlüssel aus dem Schlüsselpaar, das im Container gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="6c746-109">In this case, the [ICLRStrongName::StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md) method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="6c746-110">Wenn `pbKeyBlob` nicht NULL ist, wird angenommen, dass das Schlüsselpaar im Schlüssel Binary Large Object (BLOB) enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="6c746-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="6c746-111">Die Schlüssel müssen 1024-Bit-Rivest-Shamir-Adleman (RSA)-Signatur Schlüssel sein.</span><span class="sxs-lookup"><span data-stu-id="6c746-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="6c746-112">Zurzeit werden keine anderen Schlüsseltypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6c746-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="6c746-113">in Ein Zeiger auf das Paar aus öffentlichem und privatem Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="6c746-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="6c746-114">Dieses Paar weist das Format auf, das von der Win32-Funktion erstellt wird `CryptExportKey` .</span><span class="sxs-lookup"><span data-stu-id="6c746-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="6c746-115">Wenn `pbKeyBlob` NULL ist, wird angenommen, dass der von angegebene Schlüssel Container `szKeyContainer` das Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="6c746-115">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="6c746-116">in Die Größe von in Bytes `pbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="6c746-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="6c746-117">vorgenommen Das zurückgegebene BLOB für öffentliche Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="6c746-117">[out] The returned public key BLOB.</span></span> <span data-ttu-id="6c746-118">Der `ppbPublicKeyBlob` -Parameter wird vom Common Language Runtime zugeordnet und an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6c746-118">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="6c746-119">Der Aufrufer muss den Speicher mithilfe der [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) -Methode freigeben.</span><span class="sxs-lookup"><span data-stu-id="6c746-119">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="6c746-120">vorgenommen Die Größe des zurückgegebenen BLOBs für öffentliche Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="6c746-120">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c746-121">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6c746-121">Return Value</span></span>  

 <span data-ttu-id="6c746-122">`S_OK` , wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="6c746-122">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c746-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6c746-123">Remarks</span></span>  

 <span data-ttu-id="6c746-124">Der öffentliche Schlüssel ist in einer [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) -Struktur enthalten.</span><span class="sxs-lookup"><span data-stu-id="6c746-124">The public key is contained in a [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c746-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6c746-125">Requirements</span></span>  

 <span data-ttu-id="6c746-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c746-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c746-127">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="6c746-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6c746-128">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6c746-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6c746-129">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c746-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c746-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6c746-130">See also</span></span>

- [<span data-ttu-id="6c746-131">StrongNameTokenFromPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="6c746-131">StrongNameTokenFromPublicKey Method</span></span>](iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="6c746-132">PublicKeyBlob-Struktur</span><span class="sxs-lookup"><span data-stu-id="6c746-132">PublicKeyBlob Structure</span></span>](../strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="6c746-133">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6c746-133">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
