---
title: ICLRStrongName::StrongNameSignatureGenerationEx-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx method [.NET Framework hosting]
- StrongNameSignatureGenerationEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: c3f34584-c6e2-41fd-bb44-e44da8546309
topic_type:
- apiref
ms.openlocfilehash: 34614fe24127787a113bab4975a50f1c8d2d875e
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899496"
---
# <a name="iclrstrongnamestrongnamesignaturegenerationex-method"></a><span data-ttu-id="933f6-102">ICLRStrongName::StrongNameSignatureGenerationEx-Methode</span><span class="sxs-lookup"><span data-stu-id="933f6-102">ICLRStrongName::StrongNameSignatureGenerationEx Method</span></span>
<span data-ttu-id="933f6-103">Generiert gemäß den angegebenen Flags eine Signatur mit starkem Namen für die angegebene Assembly.</span><span class="sxs-lookup"><span data-stu-id="933f6-103">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="933f6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="933f6-104">Syntax</span></span>  
  
```cpp
HRESULT StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="933f6-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="933f6-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="933f6-106">in Der Pfad zu der Datei, die das Manifest der Assembly enthält, für die die starke namens Signatur generiert wird.</span><span class="sxs-lookup"><span data-stu-id="933f6-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="933f6-107">in Der Name des Schlüssel Containers, der das Paar aus öffentlichem und privatem Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="933f6-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="933f6-108">Wenn `pbKeyBlob` NULL ist, muss `wszKeyContainer` einen gültigen Container innerhalb des Kryptografiedienstanbieters (kryptografischen Service Provider, CSP) angeben.</span><span class="sxs-lookup"><span data-stu-id="933f6-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="933f6-109">In diesem Fall wird das im Container gespeicherte Schlüsselpaar zum Signieren der Datei verwendet.</span><span class="sxs-lookup"><span data-stu-id="933f6-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="933f6-110">Wenn `pbKeyBlob` nicht NULL ist, wird angenommen, dass das Schlüsselpaar im Schlüssel Binary Large Object (BLOB) enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="933f6-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="933f6-111">in Ein Zeiger auf das Paar aus öffentlichem und privatem Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="933f6-111">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="933f6-112">Dieses Paar weist das Format auf, das von der Win32-`CryptExportKey`-Funktion erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="933f6-112">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="933f6-113">Wenn `pbKeyBlob` NULL ist, wird angenommen, dass der von `wszKeyContainer` angegebene Schlüssel Container das Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="933f6-113">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="933f6-114">in Die Größe `pbKeyBlob`in Byte.</span><span class="sxs-lookup"><span data-stu-id="933f6-114">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="933f6-115">vorgenommen Ein Zeiger auf den Speicherort, an den der Common Language Runtime die Signatur zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="933f6-115">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="933f6-116">Wenn `ppbSignatureBlob` NULL ist, speichert die Laufzeit die Signatur in der durch `wszFilePath`angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="933f6-116">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="933f6-117">Wenn `ppbSignatureBlob` nicht NULL ist, ordnet die Common Language Runtime Speicherplatz zu, in dem die Signatur zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="933f6-117">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="933f6-118">Der Aufrufer muss diesen Bereich mithilfe der [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) -Methode freigeben.</span><span class="sxs-lookup"><span data-stu-id="933f6-118">The caller must free this space using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="933f6-119">vorgenommen Die Größe (in Bytes) der zurückgegebenen Signatur.</span><span class="sxs-lookup"><span data-stu-id="933f6-119">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="933f6-120">in Einer oder mehrere der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="933f6-120">[in] One or more of the following values:</span></span>  
  
- <span data-ttu-id="933f6-121">`SN_SIGN_ALL_FILES` (0x00000001)-Alle Hashes für verknüpfte Module neu berechnen.</span><span class="sxs-lookup"><span data-stu-id="933f6-121">`SN_SIGN_ALL_FILES` (0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
- <span data-ttu-id="933f6-122">`SN_TEST_SIGN` (0x00000002): die Assembly wird getestet.</span><span class="sxs-lookup"><span data-stu-id="933f6-122">`SN_TEST_SIGN` (0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="933f6-123">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="933f6-123">Return Value</span></span>  
 <span data-ttu-id="933f6-124">`S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="933f6-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="933f6-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="933f6-125">Remarks</span></span>  
 <span data-ttu-id="933f6-126">Geben Sie NULL für `wszFilePath` an, um die Größe der Signatur zu berechnen, ohne die Signatur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="933f6-126">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="933f6-127">Die Signatur kann entweder direkt in der Datei gespeichert oder an den Aufrufer zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="933f6-127">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="933f6-128">Wenn `SN_SIGN_ALL_FILES` angegeben ist, aber kein öffentlicher Schlüssel enthalten ist (sowohl `pbKeyBlob` als auch `wszFilePath` sind null), werden Hashwerte für verknüpfte Module neu berechnet, die Assembly wird jedoch nicht neu signiert.</span><span class="sxs-lookup"><span data-stu-id="933f6-128">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="933f6-129">Wenn `SN_TEST_SIGN` angegeben wird, wird der Common Language Runtime Header nicht geändert, um anzugeben, dass die Assembly mit einem starken Namen signiert ist.</span><span class="sxs-lookup"><span data-stu-id="933f6-129">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="933f6-130">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="933f6-130">Requirements</span></span>  
 <span data-ttu-id="933f6-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="933f6-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="933f6-132">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="933f6-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="933f6-133">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="933f6-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="933f6-134">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="933f6-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="933f6-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="933f6-135">See also</span></span>

- [<span data-ttu-id="933f6-136">StrongNameSignatureGeneration-Methode</span><span class="sxs-lookup"><span data-stu-id="933f6-136">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="933f6-137">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="933f6-137">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
