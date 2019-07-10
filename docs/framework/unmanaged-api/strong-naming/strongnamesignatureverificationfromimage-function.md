---
title: StrongNameSignatureVerificationFromImage-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- StrongnameSignatureVerificationFromImage function [.NET Framework strong naming]
ms.assetid: 9fb144d2-07e0-4a0e-8e05-907bbb6c9e03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: df2eb9d454f2037ef5f2a09d1309d52a8365e715
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782690"
---
# <a name="strongnamesignatureverificationfromimage-function"></a><span data-ttu-id="49b13-102">StrongNameSignatureVerificationFromImage-Funktion</span><span class="sxs-lookup"><span data-stu-id="49b13-102">StrongNameSignatureVerificationFromImage Function</span></span>
<span data-ttu-id="49b13-103">Überprüft, ob eine Assembly, die bereits im Speicher zugeordnet wurde, für den zugehörigen öffentlichen Schlüssel gültig ist.</span><span class="sxs-lookup"><span data-stu-id="49b13-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
 <span data-ttu-id="49b13-104">Diese Funktion wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="49b13-104">This function has been deprecated.</span></span> <span data-ttu-id="49b13-105">Verwenden der [ICLRStrongName:: StrongNameVerificationFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="49b13-105">Use the [ICLRStrongName::StrongNameVerificationFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49b13-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="49b13-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49b13-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="49b13-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="49b13-108">[in] Die relative virtuelle Adresse des Assemblymanifests zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="49b13-108">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="49b13-109">[in] Die Größe in Bytes, der das zugeordnete Bild.</span><span class="sxs-lookup"><span data-stu-id="49b13-109">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="49b13-110">[in] Flags, die Überprüfung Verhalten zu beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="49b13-110">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="49b13-111">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="49b13-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="49b13-112">`SN_INFLAG_FORCE_VER` (0 x 00000001) - Überprüfung erzwungen, selbst wenn die registrierungseinstellungen außer Kraft gesetzt werden muss.</span><span class="sxs-lookup"><span data-stu-id="49b13-112">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="49b13-113">`SN_INFLAG_INSTALL` (0 x 00000002) – gibt an, dass dies die erste überprüfungsanforderung für dieses Image ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="49b13-113">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
- <span data-ttu-id="49b13-114">`SN_INFLAG_ADMIN_ACCESS` (0 x 00000004) – gibt an, dass der Cache Zugriff nur für Benutzer gewähren, die über Administratorrechte verfügen.</span><span class="sxs-lookup"><span data-stu-id="49b13-114">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="49b13-115">`SN_INFLAG_USER_ACCESS` (0 x 00000008) – gibt an, dass die Assembly nur auf den aktuellen Benutzer zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="49b13-115">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="49b13-116">`SN_INFLAG_ALL_ACCESS` (0 x 00000010) – gibt an, dass der Cache keine Garantie für die zugriffsbeschränkung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="49b13-116">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="49b13-117">`SN_INFLAG_RUNTIME` (0 x 80000000) – reserviert für interne Debuggen.</span><span class="sxs-lookup"><span data-stu-id="49b13-117">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="49b13-118">[out] Ein Flag für zusätzliche ausgegebenen Informationen.</span><span class="sxs-lookup"><span data-stu-id="49b13-118">[out] A flag for additional output information.</span></span> <span data-ttu-id="49b13-119">Der folgende Wert wird unterstützt:</span><span class="sxs-lookup"><span data-stu-id="49b13-119">The following value is supported:</span></span>  
  
- <span data-ttu-id="49b13-120">`SN_OUTFLAG_WAS_VERIFIED` (0 x 00000001) – dieser Wert wird festgelegt, um `false` um anzugeben, dass aufgrund von registrierungseinstellungen für die Überprüfung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="49b13-120">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49b13-121">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="49b13-121">Return Value</span></span>  
 <span data-ttu-id="49b13-122">`true` Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="49b13-122">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49b13-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="49b13-123">Remarks</span></span>  
 <span data-ttu-id="49b13-124">Wenn die `StrongNameSignatureVerificationFromImage` Funktion nicht erfolgreich abgeschlossen wurde, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="49b13-124">If the `StrongNameSignatureVerificationFromImage` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49b13-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="49b13-125">Requirements</span></span>  
 <span data-ttu-id="49b13-126">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49b13-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49b13-127">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="49b13-127">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="49b13-128">**Bibliothek:** Als Ressource in mscoree.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="49b13-128">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="49b13-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49b13-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49b13-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49b13-130">See also</span></span>

- [<span data-ttu-id="49b13-131">StrongNameSignatureVerificationFromImage-Methode</span><span class="sxs-lookup"><span data-stu-id="49b13-131">StrongNameSignatureVerificationFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)
- [<span data-ttu-id="49b13-132">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49b13-132">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
