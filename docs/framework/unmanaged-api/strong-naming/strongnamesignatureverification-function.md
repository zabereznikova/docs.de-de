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
ms.openlocfilehash: 8943df861b1bff2b28c68d0233fc336d1b5d4579
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798948"
---
# <a name="strongnamesignatureverification-function"></a><span data-ttu-id="882a7-102">StrongNameSignatureVerification-Funktion</span><span class="sxs-lookup"><span data-stu-id="882a7-102">StrongNameSignatureVerification Function</span></span>
<span data-ttu-id="882a7-103">Ruft einen Wert ab, der angibt, ob das Assemblymanifest im angegebenen Pfad eine Signatur mit starkem Namen enthält, die gemäß den angegebenen Flags überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="882a7-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
 <span data-ttu-id="882a7-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="882a7-104">This function has been deprecated.</span></span> <span data-ttu-id="882a7-105">Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameSignatureVerification](../hosting/iclrstrongname-strongnamesignatureverification-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="882a7-105">Use the [ICLRStrongName::StrongNameSignatureVerification](../hosting/iclrstrongname-strongnamesignatureverification-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="882a7-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="882a7-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="882a7-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="882a7-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="882a7-108">in Der Pfad zur portablen ausführbaren Datei (dll-oder exe-Datei) für die zu überprüfende Assembly.</span><span class="sxs-lookup"><span data-stu-id="882a7-108">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="882a7-109">in Flags zum Ändern des Überprüfungs Verhaltens.</span><span class="sxs-lookup"><span data-stu-id="882a7-109">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="882a7-110">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="882a7-110">The following values are supported:</span></span>  
  
- <span data-ttu-id="882a7-111">`SN_INFLAG_FORCE_VER`(0x00000001): erzwingt die Überprüfung, auch wenn es erforderlich ist, Registrierungs Einstellungen zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="882a7-111">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="882a7-112">`SN_INFLAG_INSTALL`(0x00000002): gibt an, dass dies das erste Mal ist, wenn das Manifest überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="882a7-112">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
- <span data-ttu-id="882a7-113">`SN_INFLAG_ADMIN_ACCESS`(0x00000004): gibt an, dass der Cache nur Benutzern mit Administratorrechten Zugriff gestattet.</span><span class="sxs-lookup"><span data-stu-id="882a7-113">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="882a7-114">`SN_INFLAG_USER_ACCESS`(0x00000008): gibt an, dass die Assembly nur für den aktuellen Benutzer zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="882a7-114">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="882a7-115">`SN_INFLAG_ALL_ACCESS`(0x00000010): gibt an, dass der Cache keine Garantien für die Zugriffsbeschränkung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="882a7-115">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="882a7-116">`SN_INFLAG_RUNTIME`(0x80000000): reserviert für das interne Debuggen.</span><span class="sxs-lookup"><span data-stu-id="882a7-116">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="882a7-117">vorgenommen Flags, die angeben, ob die starke namens Signatur überprüft wurde.</span><span class="sxs-lookup"><span data-stu-id="882a7-117">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="882a7-118">Der folgende Wert wird unterstützt:</span><span class="sxs-lookup"><span data-stu-id="882a7-118">The following value is supported:</span></span>  
  
- <span data-ttu-id="882a7-119">`SN_OUTFLAG_WAS_VERIFIED`(0x00000001): dieser Wert wird auf `false` festgelegt, um anzugeben, dass die Überprüfung aufgrund von Registrierungs Einstellungen erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="882a7-119">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="882a7-120">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="882a7-120">Return Value</span></span>  
 <span data-ttu-id="882a7-121">`true`, wenn die Überprüfung erfolgreich war. `false`andernfalls.</span><span class="sxs-lookup"><span data-stu-id="882a7-121">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="882a7-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="882a7-122">Requirements</span></span>  
 <span data-ttu-id="882a7-123">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="882a7-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="882a7-124">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="882a7-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="882a7-125">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="882a7-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="882a7-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="882a7-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="882a7-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="882a7-127">See also</span></span>

- [<span data-ttu-id="882a7-128">StrongNameSignatureVerification-Methode</span><span class="sxs-lookup"><span data-stu-id="882a7-128">StrongNameSignatureVerification Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="882a7-129">StrongNameSignatureVerificationEx-Methode</span><span class="sxs-lookup"><span data-stu-id="882a7-129">StrongNameSignatureVerificationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="882a7-130">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="882a7-130">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
