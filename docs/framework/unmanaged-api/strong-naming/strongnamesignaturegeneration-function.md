---
title: StrongNameSignatureGeneration-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGeneration
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration function [.NET Framework strong naming]
ms.assetid: 839b765c-3e41-44ce-bf1b-dc10453db18e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48cdd550e5d8c7c75a603d74456e99a066d5c599
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798966"
---
# <a name="strongnamesignaturegeneration-function"></a><span data-ttu-id="5f007-102">StrongNameSignatureGeneration-Funktion</span><span class="sxs-lookup"><span data-stu-id="5f007-102">StrongNameSignatureGeneration Function</span></span>
<span data-ttu-id="5f007-103">Generiert eine Signatur mit starkem Namen für die angegebene Assembly.</span><span class="sxs-lookup"><span data-stu-id="5f007-103">Generates a strong name signature for the specified assembly.</span></span>  
  
 <span data-ttu-id="5f007-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="5f007-104">This function has been deprecated.</span></span> <span data-ttu-id="5f007-105">Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="5f007-105">Use the [ICLRStrongName::StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f007-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="5f007-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureGeneration (   
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f007-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="5f007-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="5f007-108">in Der Pfad zu der Datei, die das Manifest der Assembly enthält, für die die starke namens Signatur generiert wird.</span><span class="sxs-lookup"><span data-stu-id="5f007-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="5f007-109">in Der Name des Schlüssel Containers, der das Paar aus öffentlichem und privatem Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="5f007-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="5f007-110">Wenn `pbKeyBlob` NULL ist, `wszKeyContainer` muss einen gültigen Container innerhalb des Kryptografiedienstanbieters (kryptografischen Service Provider, CSP) angeben.</span><span class="sxs-lookup"><span data-stu-id="5f007-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="5f007-111">In diesem Fall wird das im Container gespeicherte Schlüsselpaar zum Signieren der Datei verwendet.</span><span class="sxs-lookup"><span data-stu-id="5f007-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="5f007-112">Wenn `pbKeyBlob` nicht NULL ist, wird angenommen, dass das Schlüsselpaar im Schlüssel Binary Large Object (BLOB) enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="5f007-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="5f007-113">Die Schlüssel müssen 1024-Bit-Rivest-Shamir-Adleman (RSA)-Signatur Schlüssel sein.</span><span class="sxs-lookup"><span data-stu-id="5f007-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="5f007-114">Zurzeit werden keine anderen Schlüsseltypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5f007-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="5f007-115">in Ein Zeiger auf das Paar aus öffentlichem und privatem Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="5f007-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="5f007-116">Dieses Paar weist das Format auf, das von der `CryptExportKey` Win32-Funktion erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="5f007-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="5f007-117">Wenn `pbKeyBlob` NULL ist, wird angenommen, dass der `wszKeyContainer` von angegebene Schlüssel Container das Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="5f007-117">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="5f007-118">in Die Größe von `pbKeyBlob`in Bytes.</span><span class="sxs-lookup"><span data-stu-id="5f007-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="5f007-119">vorgenommen Ein Zeiger auf den Speicherort, an den der Common Language Runtime die Signatur zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="5f007-119">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="5f007-120">Wenn `ppbSignatureBlob` NULL ist, speichert die Laufzeit die Signatur in der durch `wszFilePath`angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="5f007-120">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="5f007-121">Wenn `ppbSignatureBlob` nicht NULL ist, ordnet die Common Language Runtime Speicherplatz zu, in dem die Signatur zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="5f007-121">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="5f007-122">Der Aufrufer muss diesen Bereich mit der [StrongNameFreeBuffer](strongnamefreebuffer-function.md) -Funktion freigeben.</span><span class="sxs-lookup"><span data-stu-id="5f007-122">The caller must free this space using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="5f007-123">vorgenommen Die Größe (in Bytes) der zurückgegebenen Signatur.</span><span class="sxs-lookup"><span data-stu-id="5f007-123">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f007-124">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5f007-124">Return Value</span></span>  
 <span data-ttu-id="5f007-125">`true`nach erfolgreichem Abschluss: `false`andernfalls.</span><span class="sxs-lookup"><span data-stu-id="5f007-125">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f007-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5f007-126">Remarks</span></span>  
 <span data-ttu-id="5f007-127">Geben Sie NULL `wszFilePath` für an, um die Größe der Signatur zu berechnen, ohne die Signatur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5f007-127">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="5f007-128">Die Signatur kann entweder direkt in der Datei gespeichert oder an den Aufrufer zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5f007-128">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="5f007-129">Wenn die `StrongNameSignatureGeneration` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="5f007-129">If the `StrongNameSignatureGeneration` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f007-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5f007-130">Requirements</span></span>  
 <span data-ttu-id="5f007-131">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f007-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f007-132">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="5f007-132">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="5f007-133">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5f007-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5f007-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f007-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f007-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f007-135">See also</span></span>

- [<span data-ttu-id="5f007-136">StrongNameSignatureGeneration-Methode</span><span class="sxs-lookup"><span data-stu-id="5f007-136">StrongNameSignatureGeneration Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="5f007-137">StrongNameSignatureGenerationEx-Methode</span><span class="sxs-lookup"><span data-stu-id="5f007-137">StrongNameSignatureGenerationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="5f007-138">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5f007-138">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
