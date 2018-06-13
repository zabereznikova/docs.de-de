---
title: StrongNameGetPublicKey-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameGetPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey function [.NET Framework strong naming]
ms.assetid: 5b58c87f-3f72-40df-9b9a-291076931cc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3ace4a3103231f776d4e2b034f8e18ce861ee97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461012"
---
# <a name="strongnamegetpublickey-function"></a><span data-ttu-id="6faa7-102">StrongNameGetPublicKey-Funktion</span><span class="sxs-lookup"><span data-stu-id="6faa7-102">StrongNameGetPublicKey Function</span></span>
<span data-ttu-id="6faa7-103">Ruft den öffentlichen Schlüssel aus einem Schlüsselpaar mit privaten und öffentlichen ab.</span><span class="sxs-lookup"><span data-stu-id="6faa7-103">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="6faa7-104">Das Schlüsselpaar kann entweder als einen Schlüsselcontainernamen in einen Kryptografiedienstanbieter (CSP) oder als eine Auflistung unformatierten Bytes bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6faa7-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
 <span data-ttu-id="6faa7-105">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="6faa7-105">This function has been deprecated.</span></span> <span data-ttu-id="6faa7-106">Verwenden der [ICLRStrongName:: StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="6faa7-106">Use the [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6faa7-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="6faa7-107">Syntax</span></span>  
  
```  
BOOLEAN StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6faa7-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="6faa7-108">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="6faa7-109">[in] Der Name des Schlüsselcontainers an, die das öffentlich/privat-Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="6faa7-109">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="6faa7-110">Wenn `pbKeyBlob` ist null, `szKeyContainer` müssen einen gültigen Container im CSP angeben.</span><span class="sxs-lookup"><span data-stu-id="6faa7-110">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="6faa7-111">In diesem Fall `StrongNameGetPublicKey` extrahiert den öffentlichen Schlüssel aus dem Schlüsselpaar in dem Container gespeichert.</span><span class="sxs-lookup"><span data-stu-id="6faa7-111">In this case, `StrongNameGetPublicKey` extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="6faa7-112">Wenn `pbKeyBlob` ist ungleich null, das Schlüsselpaar wird davon ausgegangen, dass im Schlüssel binary large Object (BLOB) enthalten sein soll.</span><span class="sxs-lookup"><span data-stu-id="6faa7-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="6faa7-113">Die Schlüssel müssen 1024-Bit-Rivest-Shamir-Adleman (RSA) Signaturschlüssel sein.</span><span class="sxs-lookup"><span data-stu-id="6faa7-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="6faa7-114">Zu diesem Zeitpunkt werden keine anderen Arten von Schlüsseln unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6faa7-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="6faa7-115">[in] Ein Zeiger auf das öffentlich/privat-Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="6faa7-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="6faa7-116">Dieses Paar weist das Format, das erstellt wird, durch die Win32- `CryptExportKey` Funktion.</span><span class="sxs-lookup"><span data-stu-id="6faa7-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="6faa7-117">Wenn `pbKeyBlob` null ist, die vom angegebenen Schlüsselcontainer `szKeyContainer` wird davon ausgegangen, dass das Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="6faa7-117">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="6faa7-118">[in] Die Größe in Bytes, der `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="6faa7-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="6faa7-119">[out] Der zurückgegebene öffentliche Schlüssel BLOB.</span><span class="sxs-lookup"><span data-stu-id="6faa7-119">[out] The returned public key BLOB.</span></span> <span data-ttu-id="6faa7-120">Die `ppbPublicKeyBlob` Parameter von der common Language Runtime zugeordnet ist und an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6faa7-120">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="6faa7-121">Der Aufrufer muss den Arbeitsspeicher freigeben, mithilfe der [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="6faa7-121">The caller must free the memory by using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="6faa7-122">[out] Die Größe des BLOB zurückgegebenen öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="6faa7-122">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6faa7-123">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6faa7-123">Return Value</span></span>  
 <span data-ttu-id="6faa7-124">`true` Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="6faa7-124">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6faa7-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6faa7-125">Remarks</span></span>  
 <span data-ttu-id="6faa7-126">Der öffentliche Schlüssel ist Bestandteil einer [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) Struktur.</span><span class="sxs-lookup"><span data-stu-id="6faa7-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
 <span data-ttu-id="6faa7-127">Wenn die `StrongNameGetPublicKey` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="6faa7-127">If the `StrongNameGetPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6faa7-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6faa7-128">Requirements</span></span>  
 <span data-ttu-id="6faa7-129">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6faa7-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6faa7-130">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="6faa7-130">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="6faa7-131">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6faa7-131">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6faa7-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6faa7-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6faa7-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6faa7-133">See Also</span></span>  
 [<span data-ttu-id="6faa7-134">StrongNameGetPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="6faa7-134">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)  
 [<span data-ttu-id="6faa7-135">StrongNameTokenFromPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="6faa7-135">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [<span data-ttu-id="6faa7-136">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6faa7-136">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 [<span data-ttu-id="6faa7-137">PublicKeyBlob-Struktur</span><span class="sxs-lookup"><span data-stu-id="6faa7-137">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
