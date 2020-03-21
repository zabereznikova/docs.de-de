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
ms.openlocfilehash: fcdd4a3f07b4499fd2388b5d165c409da9150466
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176928"
---
# <a name="strongnamegetpublickey-function"></a><span data-ttu-id="b6809-102">StrongNameGetPublicKey-Funktion</span><span class="sxs-lookup"><span data-stu-id="b6809-102">StrongNameGetPublicKey Function</span></span>
<span data-ttu-id="b6809-103">Ruft den öffentlichen Schlüssel aus einem privaten/öffentlichen Schlüsselpaar ab.</span><span class="sxs-lookup"><span data-stu-id="b6809-103">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="b6809-104">Das Schlüsselpaar kann entweder als Schlüsselcontainername innerhalb eines Kryptografiedienstanbieters (Cryptographic Service Provider, CSP) oder als unformatierte Auflistung von Bytes angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b6809-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
 <span data-ttu-id="b6809-105">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="b6809-105">This function has been deprecated.</span></span> <span data-ttu-id="b6809-106">Verwenden Sie stattdessen die [ICLRStrongName::StrongNameGetPublicKey-Methode.](../hosting/iclrstrongname-strongnamegetpublickey-method.md)</span><span class="sxs-lookup"><span data-stu-id="b6809-106">Use the [ICLRStrongName::StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6809-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="b6809-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6809-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="b6809-108">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="b6809-109">[in] Der Name des Schlüsselcontainers, der das öffentliche/private Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="b6809-109">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="b6809-110">Wenn `pbKeyBlob` null `szKeyContainer` ist, muss ein gültiger Container innerhalb des CSP angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b6809-110">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="b6809-111">`StrongNameGetPublicKey` In diesem Fall wird der öffentliche Schlüssel aus dem im Container gespeicherten Schlüsselpaar extrahiert.</span><span class="sxs-lookup"><span data-stu-id="b6809-111">In this case, `StrongNameGetPublicKey` extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="b6809-112">Wenn `pbKeyBlob` es nicht null ist, wird davon ausgegangen, dass das Schlüsselpaar im PpbLOB (Key Binary Large Object) enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="b6809-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="b6809-113">Die Schlüssel müssen 1024-Bit Rivest-Shamir-Adleman (RSA) Signaturschlüssel sein.</span><span class="sxs-lookup"><span data-stu-id="b6809-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="b6809-114">Derzeit werden keine anderen Schlüsseltypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b6809-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="b6809-115">[in] Ein Zeiger auf das öffentliche/private Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="b6809-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="b6809-116">Dieses Paar hat das Format, das `CryptExportKey` von der Win32-Funktion erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b6809-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="b6809-117">Wenn `pbKeyBlob` null ist, wird `szKeyContainer` davon ausgegangen, dass der von festgelegte Schlüsselcontainer das Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="b6809-117">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="b6809-118">[in] Die Größe von in `pbKeyBlob`Bytes von .</span><span class="sxs-lookup"><span data-stu-id="b6809-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="b6809-119">[out] Der zurückgegebene BLOB des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="b6809-119">[out] The returned public key BLOB.</span></span> <span data-ttu-id="b6809-120">Der `ppbPublicKeyBlob` Parameter wird von der Common Language Runtime zugewiesen und an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b6809-120">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="b6809-121">Der Aufrufer muss den Speicher mithilfe der [StrongNameFreeBuffer-Funktion](strongnamefreebuffer-function.md) freimachen.</span><span class="sxs-lookup"><span data-stu-id="b6809-121">The caller must free the memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="b6809-122">[out] Die Größe des zurückgegebenen bLOB für den öffentlichen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="b6809-122">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b6809-123">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b6809-123">Return Value</span></span>  
 <span data-ttu-id="b6809-124">`true`bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="b6809-124">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6809-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b6809-125">Remarks</span></span>  
 <span data-ttu-id="b6809-126">Der öffentliche Schlüssel ist in einer [PublicKeyBlob-Struktur](publickeyblob-structure.md) enthalten.</span><span class="sxs-lookup"><span data-stu-id="b6809-126">The public key is contained in a [PublicKeyBlob](publickeyblob-structure.md) structure.</span></span>  
  
 <span data-ttu-id="b6809-127">Wenn `StrongNameGetPublicKey` die Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo-Funktion](strongnameerrorinfo-function.md) auf, um den zuletzt generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b6809-127">If the `StrongNameGetPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6809-128">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b6809-128">Requirements</span></span>  
 <span data-ttu-id="b6809-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6809-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6809-130">**Kopfzeile:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="b6809-130">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="b6809-131">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b6809-131">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b6809-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6809-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6809-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b6809-133">See also</span></span>

- [<span data-ttu-id="b6809-134">StrongNameGetPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="b6809-134">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="b6809-135">StrongNameTokenFromPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="b6809-135">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="b6809-136">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b6809-136">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="b6809-137">PublicKeyBlob-Struktur</span><span class="sxs-lookup"><span data-stu-id="b6809-137">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
