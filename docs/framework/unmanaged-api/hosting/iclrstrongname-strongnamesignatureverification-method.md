---
title: ICLRStrongName::StrongNameSignatureVerification-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerification
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerification method [.NET Framework hosting]
- StrongNameSignatureVerification method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 734dc4d1-0a76-4736-b5ac-cb4253b3dd49
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b773203ef390122626ea3c51644e43e571740ca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569309"
---
# <a name="iclrstrongnamestrongnamesignatureverification-method"></a><span data-ttu-id="d2bd9-102">ICLRStrongName::StrongNameSignatureVerification-Methode</span><span class="sxs-lookup"><span data-stu-id="d2bd9-102">ICLRStrongName::StrongNameSignatureVerification Method</span></span>
<span data-ttu-id="d2bd9-103">Ruft einen Wert, der angibt, ob das Assemblymanifest im angegebenen Pfad eine Signatur mit starkem Namen enthält, die gemäß den angegebenen Flags überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="d2bd9-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2bd9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2bd9-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d2bd9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d2bd9-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="d2bd9-106">[in] Der Pfad der übertragbaren ausführbaren Datei (.dll oder .exe) Datei für die Assembly aus, um zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d2bd9-106">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="d2bd9-107">[in] Flags, die das Verhalten für die Überprüfung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d2bd9-107">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="d2bd9-108">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="d2bd9-108">The following values are supported:</span></span>  
  
-   <span data-ttu-id="d2bd9-109">`SN_INFLAG_FORCE_VER` (0 x 00000001) - Überprüfung erzwungen, selbst wenn die registrierungseinstellungen außer Kraft gesetzt werden muss.</span><span class="sxs-lookup"><span data-stu-id="d2bd9-109">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   <span data-ttu-id="d2bd9-110">`SN_INFLAG_INSTALL` (0 x 00000002) – gibt an, dass dies das erste Mal ist das Manifest wird überprüft.</span><span class="sxs-lookup"><span data-stu-id="d2bd9-110">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
-   <span data-ttu-id="d2bd9-111">`SN_INFLAG_ADMIN_ACCESS` (0 x 00000004) – gibt an, dass der Cache Zugriff nur für Benutzer gewähren, die über Administratorrechte verfügen.</span><span class="sxs-lookup"><span data-stu-id="d2bd9-111">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   <span data-ttu-id="d2bd9-112">`SN_INFLAG_USER_ACCESS` (0 x 00000008) – gibt an, dass die Assembly nur auf den aktuellen Benutzer zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="d2bd9-112">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   <span data-ttu-id="d2bd9-113">`SN_INFLAG_ALL_ACCESS` (0 x 00000010) – gibt an, dass der Cache keine Garantie für die zugriffsbeschränkung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="d2bd9-113">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   <span data-ttu-id="d2bd9-114">`SN_INFLAG_RUNTIME` (0 x 80000000) – reserviert für interne Debuggen.</span><span class="sxs-lookup"><span data-stu-id="d2bd9-114">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="d2bd9-115">[out] Flags, der angibt, ob die starke Namenssignatur überprüft wurde.</span><span class="sxs-lookup"><span data-stu-id="d2bd9-115">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="d2bd9-116">Der folgende Wert wird unterstützt:</span><span class="sxs-lookup"><span data-stu-id="d2bd9-116">The following value is supported:</span></span>  
  
-   <span data-ttu-id="d2bd9-117">`SN_OUTFLAG_WAS_VERIFIED` (0 x 00000001) – dieser Wert wird festgelegt, um `false` um anzugeben, dass aufgrund von registrierungseinstellungen für die Überprüfung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="d2bd9-117">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2bd9-118">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d2bd9-118">Return Value</span></span>  
 <span data-ttu-id="d2bd9-119">`S_OK` Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="d2bd9-119">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2bd9-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d2bd9-120">Requirements</span></span>  
 <span data-ttu-id="d2bd9-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2bd9-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2bd9-122">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="d2bd9-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d2bd9-123">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d2bd9-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d2bd9-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2bd9-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2bd9-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2bd9-125">See also</span></span>
- [<span data-ttu-id="d2bd9-126">StrongNameSignatureVerificationEx-Methode</span><span class="sxs-lookup"><span data-stu-id="d2bd9-126">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="d2bd9-127">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d2bd9-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
