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
ms.openlocfilehash: c97cc0c1d4c022583d0823abeff998e2ed5f719e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710973"
---
# <a name="strongnamegetpublickey-function"></a><span data-ttu-id="d3f8c-102">StrongNameGetPublicKey-Funktion</span><span class="sxs-lookup"><span data-stu-id="d3f8c-102">StrongNameGetPublicKey Function</span></span>

<span data-ttu-id="d3f8c-103">Ruft den öffentlichen Schlüssel aus einem privaten/öffentlichen Schlüsselpaar ab.</span><span class="sxs-lookup"><span data-stu-id="d3f8c-103">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="d3f8c-104">Das Schlüsselpaar kann entweder als Schlüssel Container Name innerhalb eines Kryptografiedienstanbieters (kryptografischen Service Provider, CSP) oder als unformatierte Sammlung von Bytes angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d3f8c-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
 <span data-ttu-id="d3f8c-105">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="d3f8c-105">This function has been deprecated.</span></span> <span data-ttu-id="d3f8c-106">Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="d3f8c-106">Use the [ICLRStrongName::StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3f8c-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="d3f8c-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3f8c-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="d3f8c-108">Parameters</span></span>  

 `szKeyContainer`  
 <span data-ttu-id="d3f8c-109">in Der Name des Schlüssel Containers, der das Paar aus öffentlichem und privatem Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="d3f8c-109">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="d3f8c-110">Wenn `pbKeyBlob` NULL ist, `szKeyContainer` muss einen gültigen Container innerhalb des CSP angeben.</span><span class="sxs-lookup"><span data-stu-id="d3f8c-110">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="d3f8c-111">In diesem Fall `StrongNameGetPublicKey` extrahiert den öffentlichen Schlüssel aus dem Schlüsselpaar, das im Container gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="d3f8c-111">In this case, `StrongNameGetPublicKey` extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="d3f8c-112">Wenn `pbKeyBlob` nicht NULL ist, wird angenommen, dass das Schlüsselpaar im Schlüssel Binary Large Object (BLOB) enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="d3f8c-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="d3f8c-113">Die Schlüssel müssen 1024-Bit-Rivest-Shamir-Adleman (RSA)-Signatur Schlüssel sein.</span><span class="sxs-lookup"><span data-stu-id="d3f8c-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="d3f8c-114">Zurzeit werden keine anderen Schlüsseltypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d3f8c-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="d3f8c-115">in Ein Zeiger auf das Paar aus öffentlichem und privatem Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="d3f8c-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="d3f8c-116">Dieses Paar weist das Format auf, das von der Win32-Funktion erstellt wird `CryptExportKey` .</span><span class="sxs-lookup"><span data-stu-id="d3f8c-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="d3f8c-117">Wenn `pbKeyBlob` NULL ist, wird angenommen, dass der von angegebene Schlüssel Container `szKeyContainer` das Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="d3f8c-117">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="d3f8c-118">in Die Größe von in Bytes `pbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="d3f8c-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="d3f8c-119">vorgenommen Das zurückgegebene BLOB für öffentliche Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="d3f8c-119">[out] The returned public key BLOB.</span></span> <span data-ttu-id="d3f8c-120">Der `ppbPublicKeyBlob` -Parameter wird vom Common Language Runtime zugeordnet und an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d3f8c-120">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="d3f8c-121">Der Aufrufer muss den Speicher mithilfe der [StrongNameFreeBuffer](strongnamefreebuffer-function.md) -Funktion freigeben.</span><span class="sxs-lookup"><span data-stu-id="d3f8c-121">The caller must free the memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="d3f8c-122">vorgenommen Die Größe des zurückgegebenen BLOBs für öffentliche Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="d3f8c-122">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3f8c-123">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d3f8c-123">Return Value</span></span>  

 <span data-ttu-id="d3f8c-124">`true` nach erfolgreichem Abschluss: andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="d3f8c-124">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3f8c-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d3f8c-125">Remarks</span></span>  

 <span data-ttu-id="d3f8c-126">Der öffentliche Schlüssel ist in einer [PublicKeyBlob](publickeyblob-structure.md) -Struktur enthalten.</span><span class="sxs-lookup"><span data-stu-id="d3f8c-126">The public key is contained in a [PublicKeyBlob](publickeyblob-structure.md) structure.</span></span>  
  
 <span data-ttu-id="d3f8c-127">Wenn die `StrongNameGetPublicKey` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d3f8c-127">If the `StrongNameGetPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3f8c-128">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d3f8c-128">Requirements</span></span>  

 <span data-ttu-id="d3f8c-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3f8c-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3f8c-130">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="d3f8c-130">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d3f8c-131">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d3f8c-131">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d3f8c-132">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3f8c-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3f8c-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d3f8c-133">See also</span></span>

- [<span data-ttu-id="d3f8c-134">StrongNameGetPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="d3f8c-134">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="d3f8c-135">StrongNameTokenFromPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="d3f8c-135">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="d3f8c-136">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d3f8c-136">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="d3f8c-137">PublicKeyBlob-Struktur</span><span class="sxs-lookup"><span data-stu-id="d3f8c-137">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
