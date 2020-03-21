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
ms.openlocfilehash: d7f481e5c61ec65d2e7414bd47227866f3435028
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176902"
---
# <a name="strongnamesignaturegeneration-function"></a><span data-ttu-id="7cd15-102">StrongNameSignatureGeneration-Funktion</span><span class="sxs-lookup"><span data-stu-id="7cd15-102">StrongNameSignatureGeneration Function</span></span>
<span data-ttu-id="7cd15-103">Generiert eine Signatur mit starkem Namen für die angegebene Assembly.</span><span class="sxs-lookup"><span data-stu-id="7cd15-103">Generates a strong name signature for the specified assembly.</span></span>  
  
 <span data-ttu-id="7cd15-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="7cd15-104">This function has been deprecated.</span></span> <span data-ttu-id="7cd15-105">Verwenden Sie stattdessen die [ICLRStrongName::StrongNameSignatureGeneration-Methode.](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)</span><span class="sxs-lookup"><span data-stu-id="7cd15-105">Use the [ICLRStrongName::StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cd15-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="7cd15-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="7cd15-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="7cd15-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="7cd15-108">[in] Der Pfad zur Datei, die das Manifest der Assembly enthält, für die die Signatur mit starkem Namen generiert wird.</span><span class="sxs-lookup"><span data-stu-id="7cd15-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="7cd15-109">[in] Der Name des Schlüsselcontainers, der das öffentliche/private Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="7cd15-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="7cd15-110">Wenn `pbKeyBlob` null `wszKeyContainer` ist, muss ein gültiger Container innerhalb des Kryptografiedienstanbieters (Cryptographic Service Provider, CSP) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7cd15-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="7cd15-111">In diesem Fall wird das im Container gespeicherte Schlüsselpaar zum Signieren der Datei verwendet.</span><span class="sxs-lookup"><span data-stu-id="7cd15-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="7cd15-112">Wenn `pbKeyBlob` es nicht null ist, wird davon ausgegangen, dass das Schlüsselpaar im PpbLOB (Key Binary Large Object) enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="7cd15-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="7cd15-113">Die Schlüssel müssen 1024-Bit Rivest-Shamir-Adleman (RSA) Signaturschlüssel sein.</span><span class="sxs-lookup"><span data-stu-id="7cd15-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="7cd15-114">Derzeit werden keine anderen Schlüsseltypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7cd15-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="7cd15-115">[in] Ein Zeiger auf das öffentliche/private Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="7cd15-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="7cd15-116">Dieses Paar hat das Format, das `CryptExportKey` von der Win32-Funktion erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7cd15-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="7cd15-117">Wenn `pbKeyBlob` null ist, wird `wszKeyContainer` davon ausgegangen, dass der von festgelegte Schlüsselcontainer das Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="7cd15-117">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="7cd15-118">[in] Die Größe von in `pbKeyBlob`Bytes von .</span><span class="sxs-lookup"><span data-stu-id="7cd15-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="7cd15-119">[out] Ein Zeiger auf den Speicherort, an den die Common Language Runtime die Signatur zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="7cd15-119">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="7cd15-120">Wenn `ppbSignatureBlob` null, speichert die Laufzeit die Signatur `wszFilePath`in der datei, die von angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7cd15-120">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="7cd15-121">Wenn `ppbSignatureBlob` dies nicht null ist, weist die Common Language Runtime Speicherplatz zu, in dem die Signatur zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="7cd15-121">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="7cd15-122">Der Aufrufer muss diesen Speicherplatz mithilfe der [StrongNameFreeBuffer-Funktion](strongnamefreebuffer-function.md) freizugeben.</span><span class="sxs-lookup"><span data-stu-id="7cd15-122">The caller must free this space using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="7cd15-123">[out] Die Größe der zurückgegebenen Signatur in Bytes.</span><span class="sxs-lookup"><span data-stu-id="7cd15-123">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7cd15-124">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7cd15-124">Return Value</span></span>  
 <span data-ttu-id="7cd15-125">`true`bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="7cd15-125">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7cd15-126">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7cd15-126">Remarks</span></span>  
 <span data-ttu-id="7cd15-127">Geben Sie `wszFilePath` NULL an, um die Größe der Signatur zu berechnen, ohne die Signatur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7cd15-127">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="7cd15-128">Die Signatur kann entweder direkt in der Datei gespeichert oder an den Aufrufer zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7cd15-128">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="7cd15-129">Wenn `StrongNameSignatureGeneration` die Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo-Funktion](strongnameerrorinfo-function.md) auf, um den zuletzt generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="7cd15-129">If the `StrongNameSignatureGeneration` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cd15-130">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7cd15-130">Requirements</span></span>  
 <span data-ttu-id="7cd15-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cd15-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cd15-132">**Kopfzeile:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="7cd15-132">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="7cd15-133">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7cd15-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7cd15-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cd15-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cd15-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7cd15-135">See also</span></span>

- [<span data-ttu-id="7cd15-136">StrongNameSignatureGeneration-Methode</span><span class="sxs-lookup"><span data-stu-id="7cd15-136">StrongNameSignatureGeneration Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="7cd15-137">StrongNameSignatureGenerationEx-Methode</span><span class="sxs-lookup"><span data-stu-id="7cd15-137">StrongNameSignatureGenerationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="7cd15-138">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7cd15-138">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
