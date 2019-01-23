---
title: StrongNameKeyGen-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen function [.NET Framework strong naming]
ms.assetid: 883e413a-ad2f-4f7f-b1b9-aeb8fe5b65f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 30610311d2c48f15ebd85910557892784c0cfe85
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54542495"
---
# <a name="strongnamekeygen-function"></a><span data-ttu-id="bacd0-102">StrongNameKeyGen-Funktion</span><span class="sxs-lookup"><span data-stu-id="bacd0-102">StrongNameKeyGen Function</span></span>
<span data-ttu-id="bacd0-103">Erstellt ein neues öffentliches/privates Schlüsselpaar für die Verwendung starker Namen.</span><span class="sxs-lookup"><span data-stu-id="bacd0-103">Creates a new public/private key pair for strong name use.</span></span>  
  
 <span data-ttu-id="bacd0-104">Diese Funktion wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="bacd0-104">This function has been deprecated.</span></span> <span data-ttu-id="bacd0-105">Verwenden der [ICLRStrongName:: StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="bacd0-105">Use the [ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bacd0-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="bacd0-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bacd0-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="bacd0-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="bacd0-108">[in] Der angeforderte Schlüsselcontainer-Name.</span><span class="sxs-lookup"><span data-stu-id="bacd0-108">[in] The requested key container name.</span></span> <span data-ttu-id="bacd0-109">`wszKeyContainer` muss eine nicht leere Zeichenfolge sein, oder null, um einen temporären Namen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="bacd0-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="bacd0-110">[in] Gibt an, ob den Schlüssel registriert bleiben soll.</span><span class="sxs-lookup"><span data-stu-id="bacd0-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="bacd0-111">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="bacd0-111">The following values are supported:</span></span>  
  
-   <span data-ttu-id="bacd0-112">0 x 00000000 - wird verwendet, wenn `wszKeyContainer` null ist, um einen temporären Schlüsselcontainernamen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="bacd0-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="bacd0-113">0 x 00000001 (`SN_LEAVE_KEY`) – gibt an, dass der Schlüssel registriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="bacd0-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="bacd0-114">[out] Das zurückgegebene öffentliches/privates Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="bacd0-114">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="bacd0-115">[out] Die Größe in Bytes, des `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="bacd0-115">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bacd0-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bacd0-116">Return Value</span></span>  
 <span data-ttu-id="bacd0-117">`true` Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="bacd0-117">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bacd0-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bacd0-118">Remarks</span></span>  
 <span data-ttu-id="bacd0-119">Die `StrongNameKeyGen` Funktion wird ein 1024-Bit-Schlüssel erstellt.</span><span class="sxs-lookup"><span data-stu-id="bacd0-119">The `StrongNameKeyGen` function creates a 1024-bit key.</span></span> <span data-ttu-id="bacd0-120">Nachdem der Schlüssel abgerufen werden, sollten Sie Aufrufen der [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) Funktion, um den belegten Arbeitsspeicher freizugeben.</span><span class="sxs-lookup"><span data-stu-id="bacd0-120">After the key is retrieved, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="bacd0-121">Wenn die `StrongNameKeyGen` Funktion nicht erfolgreich abgeschlossen wurde, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="bacd0-121">If the `StrongNameKeyGen` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bacd0-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bacd0-122">Requirements</span></span>  
 <span data-ttu-id="bacd0-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bacd0-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bacd0-124">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="bacd0-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="bacd0-125">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="bacd0-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bacd0-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bacd0-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bacd0-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bacd0-127">See also</span></span>
- [<span data-ttu-id="bacd0-128">StrongNameKeyGen-Methode</span><span class="sxs-lookup"><span data-stu-id="bacd0-128">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="bacd0-129">StrongNameKeyGenEx-Methode</span><span class="sxs-lookup"><span data-stu-id="bacd0-129">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="bacd0-130">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bacd0-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
