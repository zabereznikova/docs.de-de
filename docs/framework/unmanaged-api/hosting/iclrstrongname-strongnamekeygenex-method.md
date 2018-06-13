---
title: ICLRStrongName::StrongNameKeyGenEx-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGenEx
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyGenEx method [.NET Framework hosting]
- StrongNameKeyGenEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 1f8b59d0-5b72-45b8-ab74-c2b43ffc806e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b213285b3c533488cfa48198951275925c0e37ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436185"
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a><span data-ttu-id="d404b-102">ICLRStrongName::StrongNameKeyGenEx-Methode</span><span class="sxs-lookup"><span data-stu-id="d404b-102">ICLRStrongName::StrongNameKeyGenEx Method</span></span>
<span data-ttu-id="d404b-103">Generiert ein neues öffentliches/privates Schlüsselpaar mit der angegebenen Schlüsselgröße für die Verwendung der starken Namen an.</span><span class="sxs-lookup"><span data-stu-id="d404b-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d404b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d404b-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d404b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d404b-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="d404b-106">[in] Der angeforderte Schlüsselcontainer-Name.</span><span class="sxs-lookup"><span data-stu-id="d404b-106">[in] The requested key container name.</span></span> <span data-ttu-id="d404b-107">`wszKeyContainer` muss entweder eine leere Zeichenfolge oder Null, um einen temporären Namen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="d404b-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d404b-108">[in] Ein Wert, der angibt, ob der Schlüssel verlassen registriert.</span><span class="sxs-lookup"><span data-stu-id="d404b-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="d404b-109">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="d404b-109">The following values are supported:</span></span>  
  
-   <span data-ttu-id="d404b-110">0 x 00000000 – wird verwendet, wenn `wszKeyContainer` ist null, um einen temporären Schlüsselcontainernamen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="d404b-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="d404b-111">0 x 00000001 (`SN_LEAVE_KEY`) – gibt an, dass der Schlüssel registriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d404b-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="d404b-112">[in] Die angeforderte Größe des Schlüssels in Bits.</span><span class="sxs-lookup"><span data-stu-id="d404b-112">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="d404b-113">[out] Das zurückgegebene öffentlichen/privaten Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="d404b-113">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="d404b-114">[out] Die Größe in Bytes, der `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="d404b-114">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d404b-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d404b-115">Return Value</span></span>  
 <span data-ttu-id="d404b-116">`S_OK` Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [häufig auftretende HRESULT-Werte](http://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="d404b-116">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d404b-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d404b-117">Remarks</span></span>  
 <span data-ttu-id="d404b-118">Die .NET Framework-Versionen 1.0 und 1.1 erfordern eine `dwKeySize` von 1024 Bit zum Signieren einer Assembly mit einem starken Namen, Version 2.0 fügt 2048-Bit-Schlüssel unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d404b-118">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="d404b-119">Nachdem der Schlüssel abgerufen wurden, sollten Sie Aufrufen der [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) Methode, um den belegten Speicher freizugeben.</span><span class="sxs-lookup"><span data-stu-id="d404b-119">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d404b-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d404b-120">Requirements</span></span>  
 <span data-ttu-id="d404b-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d404b-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d404b-122">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="d404b-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d404b-123">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d404b-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d404b-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d404b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d404b-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d404b-125">See Also</span></span>  
 [<span data-ttu-id="d404b-126">StrongNameKeyGen-Methode</span><span class="sxs-lookup"><span data-stu-id="d404b-126">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)  
 [<span data-ttu-id="d404b-127">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d404b-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
