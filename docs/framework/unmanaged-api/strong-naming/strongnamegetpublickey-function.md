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
ms.openlocfilehash: ae87ebd0b8225f14ca029fac80528d47f5a866cf
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799058"
---
# <a name="strongnamegetpublickey-function"></a><span data-ttu-id="f9f6e-102">StrongNameGetPublicKey-Funktion</span><span class="sxs-lookup"><span data-stu-id="f9f6e-102">StrongNameGetPublicKey Function</span></span>
<span data-ttu-id="f9f6e-103">Ruft den öffentlichen Schlüssel aus einem privaten/öffentlichen Schlüsselpaar ab.</span><span class="sxs-lookup"><span data-stu-id="f9f6e-103">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="f9f6e-104">Das Schlüsselpaar kann entweder als Schlüssel Container Name innerhalb eines Kryptografiedienstanbieters (kryptografischen Service Provider, CSP) oder als unformatierte Sammlung von Bytes angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f9f6e-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
 <span data-ttu-id="f9f6e-105">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="f9f6e-105">This function has been deprecated.</span></span> <span data-ttu-id="f9f6e-106">Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="f9f6e-106">Use the [ICLRStrongName::StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9f6e-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="f9f6e-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9f6e-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="f9f6e-108">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="f9f6e-109">in Der Name des Schlüssel Containers, der das Paar aus öffentlichem und privatem Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="f9f6e-109">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="f9f6e-110">Wenn `pbKeyBlob` NULL ist, `szKeyContainer` muss einen gültigen Container innerhalb des CSP angeben.</span><span class="sxs-lookup"><span data-stu-id="f9f6e-110">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="f9f6e-111">In diesem Fall extrahiert `StrongNameGetPublicKey` den öffentlichen Schlüssel aus dem Schlüsselpaar, das im Container gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="f9f6e-111">In this case, `StrongNameGetPublicKey` extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="f9f6e-112">Wenn `pbKeyBlob` nicht NULL ist, wird angenommen, dass das Schlüsselpaar im Schlüssel Binary Large Object (BLOB) enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="f9f6e-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="f9f6e-113">Die Schlüssel müssen 1024-Bit-Rivest-Shamir-Adleman (RSA)-Signatur Schlüssel sein.</span><span class="sxs-lookup"><span data-stu-id="f9f6e-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="f9f6e-114">Zurzeit werden keine anderen Schlüsseltypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f9f6e-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="f9f6e-115">in Ein Zeiger auf das Paar aus öffentlichem und privatem Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="f9f6e-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="f9f6e-116">Dieses Paar weist das Format auf, das von der `CryptExportKey` Win32-Funktion erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f9f6e-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="f9f6e-117">Wenn `pbKeyBlob` NULL ist, wird angenommen, dass der `szKeyContainer` von angegebene Schlüssel Container das Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="f9f6e-117">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="f9f6e-118">in Die Größe von `pbKeyBlob`in Bytes.</span><span class="sxs-lookup"><span data-stu-id="f9f6e-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="f9f6e-119">vorgenommen Das zurückgegebene BLOB für öffentliche Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="f9f6e-119">[out] The returned public key BLOB.</span></span> <span data-ttu-id="f9f6e-120">Der `ppbPublicKeyBlob` -Parameter wird vom Common Language Runtime zugeordnet und an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f9f6e-120">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="f9f6e-121">Der Aufrufer muss den Speicher mithilfe der [StrongNameFreeBuffer](strongnamefreebuffer-function.md) -Funktion freigeben.</span><span class="sxs-lookup"><span data-stu-id="f9f6e-121">The caller must free the memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="f9f6e-122">vorgenommen Die Größe des zurückgegebenen BLOBs für öffentliche Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="f9f6e-122">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f9f6e-123">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f9f6e-123">Return Value</span></span>  
 <span data-ttu-id="f9f6e-124">`true`nach erfolgreichem Abschluss: `false`andernfalls.</span><span class="sxs-lookup"><span data-stu-id="f9f6e-124">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9f6e-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f9f6e-125">Remarks</span></span>  
 <span data-ttu-id="f9f6e-126">Der öffentliche Schlüssel ist in einer [PublicKeyBlob](publickeyblob-structure.md) -Struktur enthalten.</span><span class="sxs-lookup"><span data-stu-id="f9f6e-126">The public key is contained in a [PublicKeyBlob](publickeyblob-structure.md) structure.</span></span>  
  
 <span data-ttu-id="f9f6e-127">Wenn die `StrongNameGetPublicKey` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f9f6e-127">If the `StrongNameGetPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9f6e-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f9f6e-128">Requirements</span></span>  
 <span data-ttu-id="f9f6e-129">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9f6e-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9f6e-130">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="f9f6e-130">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="f9f6e-131">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f9f6e-131">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f9f6e-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9f6e-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9f6e-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9f6e-133">See also</span></span>

- [<span data-ttu-id="f9f6e-134">StrongNameGetPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="f9f6e-134">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="f9f6e-135">StrongNameTokenFromPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="f9f6e-135">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="f9f6e-136">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f9f6e-136">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="f9f6e-137">PublicKeyBlob-Struktur</span><span class="sxs-lookup"><span data-stu-id="f9f6e-137">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
