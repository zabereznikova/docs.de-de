---
title: StrongNameKeyGenEx-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameKeyGenEx
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameKeyGenEx
helpviewer_keywords: StrongNameKeyGenEx function [.NET Framework strong naming]
ms.assetid: 36bd10b9-9857-45f3-8d3b-0da091d6169e
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 87841c230c71650f822a6cb2f6cc3f3c17c2ef35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamekeygenex-function"></a><span data-ttu-id="0aa0a-102">StrongNameKeyGenEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="0aa0a-102">StrongNameKeyGenEx Function</span></span>
<span data-ttu-id="0aa0a-103">Generiert ein neues öffentliches/privates Schlüsselpaar mit der angegebenen Schlüsselgröße für die Verwendung der starken Namen an.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
 <span data-ttu-id="0aa0a-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-104">This function has been deprecated.</span></span> <span data-ttu-id="0aa0a-105">Verwenden der [ICLRStrongName:: StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-105">Use the [ICLRStrongName::StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0aa0a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="0aa0a-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0aa0a-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="0aa0a-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="0aa0a-108">[in] Der angeforderte Schlüsselcontainer-Name.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-108">[in] The requested key container name.</span></span> <span data-ttu-id="0aa0a-109">`wszKeyContainer`muss eine nicht leere Zeichenfolge sein, oder null, um einen temporären Namen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="0aa0a-110">[in] Gibt an, ob der Schlüssel registriert verlassen.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="0aa0a-111">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="0aa0a-111">The following values are supported:</span></span>  
  
-   <span data-ttu-id="0aa0a-112">0 x 00000000 – wird verwendet, wenn `wszKeyContainer` ist null, um einen temporären Schlüsselcontainernamen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="0aa0a-113">0 x 00000001 (`SN_LEAVE_KEY`) – gibt an, dass der Schlüssel registriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="0aa0a-114">[in] Die angeforderte Größe des Schlüssels in Bits.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-114">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="0aa0a-115">[out] Das zurückgegebene öffentlichen/privaten Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-115">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="0aa0a-116">[out] Die Größe in Bytes, der `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-116">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0aa0a-117">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0aa0a-117">Return Value</span></span>  
 <span data-ttu-id="0aa0a-118">`true`Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-118">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0aa0a-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0aa0a-119">Remarks</span></span>  
 <span data-ttu-id="0aa0a-120">Die .NET Framework-Versionen 1.0 und 1.1 erfordern eine `dwKeySize` von 1024 Bit zum Signieren einer Assembly mit einem starken Namen, Version 2.0 fügt 2048-Bit-Schlüssel unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-120">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="0aa0a-121">Nachdem der Schlüssel abgerufen wurden, sollten Sie Aufrufen der [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) Funktion, um den belegten Speicher freizugeben.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-121">After the key is retrieved, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="0aa0a-122">Wenn die `StrongNameKeyGenEx` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0aa0a-122">If the `StrongNameKeyGenEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0aa0a-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0aa0a-123">Requirements</span></span>  
 <span data-ttu-id="0aa0a-124">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0aa0a-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0aa0a-125">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="0aa0a-125">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="0aa0a-126">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0aa0a-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0aa0a-127">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0aa0a-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0aa0a-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0aa0a-128">See Also</span></span>  
 [<span data-ttu-id="0aa0a-129">StrongNameKeyGenEx-Methode</span><span class="sxs-lookup"><span data-stu-id="0aa0a-129">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)  
 [<span data-ttu-id="0aa0a-130">StrongNameKeyGen-Methode</span><span class="sxs-lookup"><span data-stu-id="0aa0a-130">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)  
 [<span data-ttu-id="0aa0a-131">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0aa0a-131">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
