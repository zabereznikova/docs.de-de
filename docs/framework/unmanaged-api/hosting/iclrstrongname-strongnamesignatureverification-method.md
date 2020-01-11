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
ms.openlocfilehash: 6375fd8e4a314403267a4cdf2e8356677e9e7a06
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899489"
---
# <a name="iclrstrongnamestrongnamesignatureverification-method"></a><span data-ttu-id="76ac2-102">ICLRStrongName::StrongNameSignatureVerification-Methode</span><span class="sxs-lookup"><span data-stu-id="76ac2-102">ICLRStrongName::StrongNameSignatureVerification Method</span></span>
<span data-ttu-id="76ac2-103">Ruft einen Wert ab, der angibt, ob das Assemblymanifest im angegebenen Pfad eine Signatur mit starkem Namen enthält, die entsprechend den angegebenen Flags überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="76ac2-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76ac2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="76ac2-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76ac2-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="76ac2-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="76ac2-106">in Der Pfad zur portablen ausführbaren Datei (dll-oder exe-Datei) für die zu überprüfende Assembly.</span><span class="sxs-lookup"><span data-stu-id="76ac2-106">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="76ac2-107">in Flags zum Ändern des Überprüfungs Verhaltens.</span><span class="sxs-lookup"><span data-stu-id="76ac2-107">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="76ac2-108">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="76ac2-108">The following values are supported:</span></span>  
  
- <span data-ttu-id="76ac2-109">`SN_INFLAG_FORCE_VER` (0x00000001): erzwingt die Überprüfung, auch wenn es erforderlich ist, Registrierungs Einstellungen zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="76ac2-109">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="76ac2-110">`SN_INFLAG_INSTALL` (0x00000002): gibt an, dass dies das erste Mal ist, wenn das Manifest überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="76ac2-110">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
- <span data-ttu-id="76ac2-111">`SN_INFLAG_ADMIN_ACCESS` (0x00000004): gibt an, dass der Cache nur Benutzern mit Administratorrechten den Zugriff gestattet.</span><span class="sxs-lookup"><span data-stu-id="76ac2-111">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="76ac2-112">`SN_INFLAG_USER_ACCESS` (0x00000008): gibt an, dass die Assembly nur für den aktuellen Benutzer zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="76ac2-112">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="76ac2-113">`SN_INFLAG_ALL_ACCESS` (0x00000010): gibt an, dass der Cache keine Garantien für die Zugriffsbeschränkung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="76ac2-113">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="76ac2-114">`SN_INFLAG_RUNTIME` (0x80000000): reserviert für das interne Debuggen.</span><span class="sxs-lookup"><span data-stu-id="76ac2-114">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="76ac2-115">vorgenommen Flags, die angeben, ob die starke namens Signatur überprüft wurde.</span><span class="sxs-lookup"><span data-stu-id="76ac2-115">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="76ac2-116">Der folgende Wert wird unterstützt:</span><span class="sxs-lookup"><span data-stu-id="76ac2-116">The following value is supported:</span></span>  
  
- <span data-ttu-id="76ac2-117">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001): dieser Wert wird auf `false` festgelegt, um anzugeben, dass die Überprüfung aufgrund von Registrierungs Einstellungen erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="76ac2-117">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76ac2-118">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="76ac2-118">Return Value</span></span>  
 <span data-ttu-id="76ac2-119">`S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="76ac2-119">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76ac2-120">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="76ac2-120">Requirements</span></span>  
 <span data-ttu-id="76ac2-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76ac2-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76ac2-122">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="76ac2-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="76ac2-123">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="76ac2-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="76ac2-124">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76ac2-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76ac2-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="76ac2-125">See also</span></span>

- [<span data-ttu-id="76ac2-126">StrongNameSignatureVerificationEx-Methode</span><span class="sxs-lookup"><span data-stu-id="76ac2-126">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="76ac2-127">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="76ac2-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
