---
title: StrongNameKeyGenEx-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGenEx
helpviewer_keywords:
- StrongNameKeyGenEx function [.NET Framework strong naming]
ms.assetid: 36bd10b9-9857-45f3-8d3b-0da091d6169e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e65e962d099e944fe243b3acc0a7c25a3bb960c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458669"
---
# <a name="strongnamekeygenex-function"></a><span data-ttu-id="dee46-102">StrongNameKeyGenEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="dee46-102">StrongNameKeyGenEx Function</span></span>
<span data-ttu-id="dee46-103">Generiert ein neues öffentliches/privates Schlüsselpaar mit der angegebenen Schlüsselgröße für die Verwendung der starken Namen an.</span><span class="sxs-lookup"><span data-stu-id="dee46-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
 <span data-ttu-id="dee46-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="dee46-104">This function has been deprecated.</span></span> <span data-ttu-id="dee46-105">Verwenden der [ICLRStrongName:: StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="dee46-105">Use the [ICLRStrongName::StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dee46-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="dee46-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dee46-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="dee46-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="dee46-108">[in] Der angeforderte Schlüsselcontainer-Name.</span><span class="sxs-lookup"><span data-stu-id="dee46-108">[in] The requested key container name.</span></span> <span data-ttu-id="dee46-109">`wszKeyContainer` muss eine nicht leere Zeichenfolge sein, oder null, um einen temporären Namen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="dee46-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="dee46-110">[in] Gibt an, ob der Schlüssel registriert verlassen.</span><span class="sxs-lookup"><span data-stu-id="dee46-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="dee46-111">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="dee46-111">The following values are supported:</span></span>  
  
-   <span data-ttu-id="dee46-112">0 x 00000000 – wird verwendet, wenn `wszKeyContainer` ist null, um einen temporären Schlüsselcontainernamen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="dee46-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="dee46-113">0 x 00000001 (`SN_LEAVE_KEY`) – gibt an, dass der Schlüssel registriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="dee46-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="dee46-114">[in] Die angeforderte Größe des Schlüssels in Bits.</span><span class="sxs-lookup"><span data-stu-id="dee46-114">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="dee46-115">[out] Das zurückgegebene öffentlichen/privaten Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="dee46-115">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="dee46-116">[out] Die Größe in Bytes, der `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="dee46-116">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dee46-117">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="dee46-117">Return Value</span></span>  
 <span data-ttu-id="dee46-118">`true` Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="dee46-118">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dee46-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dee46-119">Remarks</span></span>  
 <span data-ttu-id="dee46-120">Die .NET Framework-Versionen 1.0 und 1.1 erfordern eine `dwKeySize` von 1024 Bit zum Signieren einer Assembly mit einem starken Namen, Version 2.0 fügt 2048-Bit-Schlüssel unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dee46-120">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="dee46-121">Nachdem der Schlüssel abgerufen wurden, sollten Sie Aufrufen der [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) Funktion, um den belegten Speicher freizugeben.</span><span class="sxs-lookup"><span data-stu-id="dee46-121">After the key is retrieved, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="dee46-122">Wenn die `StrongNameKeyGenEx` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="dee46-122">If the `StrongNameKeyGenEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dee46-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dee46-123">Requirements</span></span>  
 <span data-ttu-id="dee46-124">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dee46-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dee46-125">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="dee46-125">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="dee46-126">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="dee46-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dee46-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dee46-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dee46-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dee46-128">See Also</span></span>  
 [<span data-ttu-id="dee46-129">StrongNameKeyGenEx-Methode</span><span class="sxs-lookup"><span data-stu-id="dee46-129">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)  
 [<span data-ttu-id="dee46-130">StrongNameKeyGen-Methode</span><span class="sxs-lookup"><span data-stu-id="dee46-130">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)  
 [<span data-ttu-id="dee46-131">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dee46-131">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
