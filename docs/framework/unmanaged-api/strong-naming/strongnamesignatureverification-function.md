---
title: StrongNameSignatureVerification-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerification
helpviewer_keywords:
- StrongNameSignatureVerification function [.NET Framework strong naming]
ms.assetid: 933758dd-231e-4382-8819-242c0a13a4b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c398663b84637d2551b0d94bd59b9e0994721ba5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61792625"
---
# <a name="strongnamesignatureverification-function"></a><span data-ttu-id="6cd49-102">StrongNameSignatureVerification-Funktion</span><span class="sxs-lookup"><span data-stu-id="6cd49-102">StrongNameSignatureVerification Function</span></span>
<span data-ttu-id="6cd49-103">Ruft einen Wert ab, der angibt, ob das Assemblymanifest im angegebenen Pfad eine Signatur mit starkem Namen enthält, die gemäß den angegebenen Flags überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="6cd49-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
 <span data-ttu-id="6cd49-104">Diese Funktion wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="6cd49-104">This function has been deprecated.</span></span> <span data-ttu-id="6cd49-105">Verwenden der [ICLRStrongName:: StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="6cd49-105">Use the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cd49-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="6cd49-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6cd49-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="6cd49-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="6cd49-108">[in] Der Pfad der übertragbaren ausführbaren Datei (.dll oder .exe) Datei für die Assembly aus, um zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6cd49-108">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="6cd49-109">[in] Flags, die das Verhalten für die Überprüfung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="6cd49-109">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="6cd49-110">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="6cd49-110">The following values are supported:</span></span>  
  
- <span data-ttu-id="6cd49-111">`SN_INFLAG_FORCE_VER` (0 x 00000001) - Überprüfung erzwungen, selbst wenn die registrierungseinstellungen außer Kraft gesetzt werden muss.</span><span class="sxs-lookup"><span data-stu-id="6cd49-111">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="6cd49-112">`SN_INFLAG_INSTALL` (0 x 00000002) – gibt an, dass dies das erste Mal ist das Manifest wird überprüft.</span><span class="sxs-lookup"><span data-stu-id="6cd49-112">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
- <span data-ttu-id="6cd49-113">`SN_INFLAG_ADMIN_ACCESS` (0 x 00000004) – gibt an, dass der Cache Zugriff nur für Benutzer gewähren, die über Administratorrechte verfügen.</span><span class="sxs-lookup"><span data-stu-id="6cd49-113">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="6cd49-114">`SN_INFLAG_USER_ACCESS` (0 x 00000008) – gibt an, dass die Assembly nur auf den aktuellen Benutzer zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="6cd49-114">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="6cd49-115">`SN_INFLAG_ALL_ACCESS` (0 x 00000010) – gibt an, dass der Cache keine Garantie für die zugriffsbeschränkung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="6cd49-115">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="6cd49-116">`SN_INFLAG_RUNTIME` (0 x 80000000) – reserviert für interne Debuggen.</span><span class="sxs-lookup"><span data-stu-id="6cd49-116">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="6cd49-117">[out] Flags, der angibt, ob die starke Namenssignatur überprüft wurde.</span><span class="sxs-lookup"><span data-stu-id="6cd49-117">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="6cd49-118">Der folgende Wert wird unterstützt:</span><span class="sxs-lookup"><span data-stu-id="6cd49-118">The following value is supported:</span></span>  
  
- <span data-ttu-id="6cd49-119">`SN_OUTFLAG_WAS_VERIFIED` (0 x 00000001) – dieser Wert wird festgelegt, um `false` um anzugeben, dass aufgrund von registrierungseinstellungen für die Überprüfung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="6cd49-119">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6cd49-120">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6cd49-120">Return Value</span></span>  
 <span data-ttu-id="6cd49-121">`true` Wenn die Überprüfung erfolgreich war; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="6cd49-121">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6cd49-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6cd49-122">Requirements</span></span>  
 <span data-ttu-id="6cd49-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6cd49-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6cd49-124">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="6cd49-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="6cd49-125">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6cd49-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6cd49-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6cd49-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cd49-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6cd49-127">See also</span></span>

- [<span data-ttu-id="6cd49-128">StrongNameSignatureVerification-Methode</span><span class="sxs-lookup"><span data-stu-id="6cd49-128">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="6cd49-129">StrongNameSignatureVerificationEx-Methode</span><span class="sxs-lookup"><span data-stu-id="6cd49-129">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="6cd49-130">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6cd49-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
