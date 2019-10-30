---
title: StrongNameSignatureGenerationEx-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGenerationEx
helpviewer_keywords:
- StrongNameSignatureGenerationEx function [.NET Framework strong naming]
ms.assetid: 9a75469e-aa49-4e32-ad48-3bafd5202f09
topic_type:
- apiref
ms.openlocfilehash: e8f63a6379af8f2b7b88c511840622d49d65d587
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141572"
---
# <a name="strongnamesignaturegenerationex-function"></a><span data-ttu-id="87f83-102">StrongNameSignatureGenerationEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="87f83-102">StrongNameSignatureGenerationEx Function</span></span>
<span data-ttu-id="87f83-103">Generiert gemäß den angegebenen Flags eine Signatur mit starkem Namen für die angegebene Assembly.</span><span class="sxs-lookup"><span data-stu-id="87f83-103">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
 <span data-ttu-id="87f83-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="87f83-104">This function has been deprecated.</span></span> <span data-ttu-id="87f83-105">Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameSignatureGenerationEx](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="87f83-105">Use the [ICLRStrongName::StrongNameSignatureGenerationEx](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87f83-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="87f83-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87f83-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="87f83-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="87f83-108">in Der Pfad zu der Datei, die das Manifest der Assembly enthält, für die die starke namens Signatur generiert wird.</span><span class="sxs-lookup"><span data-stu-id="87f83-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="87f83-109">in Der Name des Schlüssel Containers, der das Paar aus öffentlichem und privatem Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="87f83-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="87f83-110">Wenn `pbKeyBlob` NULL ist, muss `wszKeyContainer` einen gültigen Container innerhalb des Kryptografiedienstanbieters (kryptografischen Service Provider, CSP) angeben.</span><span class="sxs-lookup"><span data-stu-id="87f83-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="87f83-111">In diesem Fall wird das im Container gespeicherte Schlüsselpaar zum Signieren der Datei verwendet.</span><span class="sxs-lookup"><span data-stu-id="87f83-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="87f83-112">Wenn `pbKeyBlob` nicht NULL ist, wird angenommen, dass das Schlüsselpaar im Schlüssel Binary Large Object (BLOB) enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="87f83-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="87f83-113">in Ein Zeiger auf das Paar aus öffentlichem und privatem Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="87f83-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="87f83-114">Dieses Paar weist das Format auf, das von der Win32-`CryptExportKey`-Funktion erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="87f83-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="87f83-115">Wenn `pbKeyBlob` NULL ist, wird angenommen, dass der von `wszKeyContainer` angegebene Schlüssel Container das Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="87f83-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="87f83-116">in Die Größe `pbKeyBlob`in Byte.</span><span class="sxs-lookup"><span data-stu-id="87f83-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="87f83-117">vorgenommen Ein Zeiger auf den Speicherort, an den der Common Language Runtime die Signatur zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="87f83-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="87f83-118">Wenn `ppbSignatureBlob` NULL ist, speichert die Laufzeit die Signatur in der durch `wszFilePath`angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="87f83-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="87f83-119">Wenn `ppbSignatureBlob` nicht NULL ist, ordnet die Common Language Runtime Speicherplatz zu, in dem die Signatur zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="87f83-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="87f83-120">Der Aufrufer muss diesen Bereich mit der [StrongNameFreeBuffer](strongnamefreebuffer-function.md) -Funktion freigeben.</span><span class="sxs-lookup"><span data-stu-id="87f83-120">The caller must free this space using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="87f83-121">vorgenommen Die Größe (in Bytes) der zurückgegebenen Signatur.</span><span class="sxs-lookup"><span data-stu-id="87f83-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="87f83-122">in Einer oder mehrere der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="87f83-122">[in] One or more of the following values:</span></span>  
  
- <span data-ttu-id="87f83-123">`SN_SIGN_ALL_FILES` (0x00000001)-Alle Hashes für verknüpfte Module neu berechnen.</span><span class="sxs-lookup"><span data-stu-id="87f83-123">`SN_SIGN_ALL_FILES` (0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
- <span data-ttu-id="87f83-124">`SN_TEST_SIGN` (0x00000002): die Assembly wird getestet.</span><span class="sxs-lookup"><span data-stu-id="87f83-124">`SN_TEST_SIGN` (0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87f83-125">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="87f83-125">Return Value</span></span>  
 <span data-ttu-id="87f83-126">`true` nach erfolgreichem Abschluss. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="87f83-126">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87f83-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="87f83-127">Remarks</span></span>  
 <span data-ttu-id="87f83-128">Geben Sie NULL für `wszFilePath` an, um die Größe der Signatur zu berechnen, ohne die Signatur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="87f83-128">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="87f83-129">Die Signatur kann entweder direkt in der Datei gespeichert oder an den Aufrufer zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="87f83-129">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="87f83-130">Wenn `SN_SIGN_ALL_FILES` angegeben ist, aber kein öffentlicher Schlüssel enthalten ist (sowohl `pbKeyBlob` als auch `wszFilePath` sind null), werden Hashwerte für verknüpfte Module neu berechnet, die Assembly wird jedoch nicht neu signiert.</span><span class="sxs-lookup"><span data-stu-id="87f83-130">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="87f83-131">Wenn `SN_TEST_SIGN` angegeben wird, wird der Common Language Runtime Header nicht geändert, um anzugeben, dass die Assembly mit einem starken Namen signiert ist.</span><span class="sxs-lookup"><span data-stu-id="87f83-131">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
 <span data-ttu-id="87f83-132">Wenn die `StrongNameSignatureGenerationEx`-Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="87f83-132">If the `StrongNameSignatureGenerationEx` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87f83-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="87f83-133">Requirements</span></span>  
 <span data-ttu-id="87f83-134">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87f83-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87f83-135">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="87f83-135">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="87f83-136">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="87f83-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="87f83-137">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87f83-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87f83-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87f83-138">See also</span></span>

- [<span data-ttu-id="87f83-139">StrongNameSignatureGenerationEx-Methode</span><span class="sxs-lookup"><span data-stu-id="87f83-139">StrongNameSignatureGenerationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="87f83-140">StrongNameSignatureGeneration-Methode</span><span class="sxs-lookup"><span data-stu-id="87f83-140">StrongNameSignatureGeneration Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="87f83-141">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="87f83-141">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
