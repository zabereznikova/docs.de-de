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
ms.openlocfilehash: fd7f95ea01de397509c2a7b5fc08c0ac401a8da9
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899606"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a><span data-ttu-id="10af3-102">ICLRStrongName::StrongNameGetPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="10af3-102">ICLRStrongName::StrongNameGetPublicKey Method</span></span>
<span data-ttu-id="10af3-103">Ruft den öffentlichen Schlüssel aus einem Paar aus öffentlichem und privatem Schlüssel ab.</span><span class="sxs-lookup"><span data-stu-id="10af3-103">Gets the public key from a public/private key pair.</span></span> <span data-ttu-id="10af3-104">Das Schlüsselpaar kann entweder als Schlüssel Container Name innerhalb eines Kryptografiedienstanbieters (kryptografischen Service Provider, CSP) oder als unformatierte Sammlung von Bytes angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="10af3-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10af3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="10af3-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10af3-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="10af3-106">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="10af3-107">in Der Name des Schlüssel Containers, der das Paar aus öffentlichem und privatem Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="10af3-107">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="10af3-108">Wenn `pbKeyBlob` NULL ist, muss `szKeyContainer` einen gültigen Container innerhalb des CSP angeben.</span><span class="sxs-lookup"><span data-stu-id="10af3-108">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="10af3-109">In diesem Fall extrahiert die [ICLRStrongName:: StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) -Methode den öffentlichen Schlüssel aus dem Schlüsselpaar, das im Container gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="10af3-109">In this case, the [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="10af3-110">Wenn `pbKeyBlob` nicht NULL ist, wird angenommen, dass das Schlüsselpaar im Schlüssel Binary Large Object (BLOB) enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="10af3-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="10af3-111">Die Schlüssel müssen 1024-Bit-Rivest-Shamir-Adleman (RSA)-Signatur Schlüssel sein.</span><span class="sxs-lookup"><span data-stu-id="10af3-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="10af3-112">Zurzeit werden keine anderen Schlüsseltypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="10af3-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="10af3-113">in Ein Zeiger auf das Paar aus öffentlichem und privatem Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="10af3-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="10af3-114">Dieses Paar weist das Format auf, das von der Win32-`CryptExportKey`-Funktion erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="10af3-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="10af3-115">Wenn `pbKeyBlob` NULL ist, wird angenommen, dass der von `szKeyContainer` angegebene Schlüssel Container das Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="10af3-115">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="10af3-116">in Die Größe `pbKeyBlob`in Byte.</span><span class="sxs-lookup"><span data-stu-id="10af3-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="10af3-117">vorgenommen Das zurückgegebene BLOB für öffentliche Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="10af3-117">[out] The returned public key BLOB.</span></span> <span data-ttu-id="10af3-118">Der `ppbPublicKeyBlob`-Parameter wird vom Common Language Runtime zugeordnet und an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="10af3-118">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="10af3-119">Der Aufrufer muss den Speicher mithilfe der [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) -Methode freigeben.</span><span class="sxs-lookup"><span data-stu-id="10af3-119">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="10af3-120">vorgenommen Die Größe des zurückgegebenen BLOBs für öffentliche Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="10af3-120">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10af3-121">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="10af3-121">Return Value</span></span>  
 <span data-ttu-id="10af3-122">`S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="10af3-122">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10af3-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="10af3-123">Remarks</span></span>  
 <span data-ttu-id="10af3-124">Der öffentliche Schlüssel ist in einer [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) -Struktur enthalten.</span><span class="sxs-lookup"><span data-stu-id="10af3-124">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10af3-125">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="10af3-125">Requirements</span></span>  
 <span data-ttu-id="10af3-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10af3-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10af3-127">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="10af3-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="10af3-128">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="10af3-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="10af3-129">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10af3-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10af3-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10af3-130">See also</span></span>

- [<span data-ttu-id="10af3-131">StrongNameTokenFromPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="10af3-131">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="10af3-132">PublicKeyBlob-Struktur</span><span class="sxs-lookup"><span data-stu-id="10af3-132">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="10af3-133">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="10af3-133">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
