---
title: ICLRStrongName::StrongNameSignatureVerificationFromImage-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerificationFromImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage method [.NET Framework hosting]
- StrongNameSignatureVerificationFromImage method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: da91c138-ee30-4fd4-a040-464d97d7e41a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a7e09ac96a8803f41d78b532c9da67315e5dd6b4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113736"
---
# <a name="iclrstrongnamestrongnamesignatureverificationfromimage-method"></a><span data-ttu-id="73f20-102">ICLRStrongName::StrongNameSignatureVerificationFromImage-Methode</span><span class="sxs-lookup"><span data-stu-id="73f20-102">ICLRStrongName::StrongNameSignatureVerificationFromImage Method</span></span>
<span data-ttu-id="73f20-103">Überprüft, ob eine Assembly, die bereits im Speicher zugeordnet wurde, für den zugehörigen öffentlichen Schlüssel gültig ist.</span><span class="sxs-lookup"><span data-stu-id="73f20-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73f20-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="73f20-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73f20-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="73f20-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="73f20-106">[in] Die relative virtuelle Adresse des Assemblymanifests zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="73f20-106">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="73f20-107">[in] Die Größe in Bytes, der das zugeordnete Bild.</span><span class="sxs-lookup"><span data-stu-id="73f20-107">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="73f20-108">[in] Flags, die Überprüfung Verhalten zu beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="73f20-108">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="73f20-109">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="73f20-109">The following values are supported:</span></span>  
  
-   `SN_INFLAG_FORCE_VER` <span data-ttu-id="73f20-110">(0 x 00000001) - Überprüfung erzwungen, selbst wenn die registrierungseinstellungen außer Kraft gesetzt werden muss.</span><span class="sxs-lookup"><span data-stu-id="73f20-110">(0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   `SN_INFLAG_INSTALL` <span data-ttu-id="73f20-111">(0 x 00000002) – gibt an, dass dies die erste überprüfungsanforderung für dieses Image ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="73f20-111">(0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
-   `SN_INFLAG_ADMIN_ACCESS` <span data-ttu-id="73f20-112">(0 x 00000004) – gibt an, dass der Cache Zugriff nur für Benutzer gewähren, die über Administratorrechte verfügen.</span><span class="sxs-lookup"><span data-stu-id="73f20-112">(0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   `SN_INFLAG_USER_ACCESS` <span data-ttu-id="73f20-113">(0 x 00000008) – gibt an, dass die Assembly nur auf den aktuellen Benutzer zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="73f20-113">(0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   `SN_INFLAG_ALL_ACCESS` <span data-ttu-id="73f20-114">(0 x 00000010) – gibt an, dass der Cache keine Garantie für die zugriffsbeschränkung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="73f20-114">(0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   `SN_INFLAG_RUNTIME` <span data-ttu-id="73f20-115">(0 x 80000000) – reserviert für interne Debuggen.</span><span class="sxs-lookup"><span data-stu-id="73f20-115">(0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="73f20-116">[out] Ein Flag für zusätzliche ausgegebenen Informationen.</span><span class="sxs-lookup"><span data-stu-id="73f20-116">[out] A flag for additional output information.</span></span> <span data-ttu-id="73f20-117">Der folgende Wert wird unterstützt:</span><span class="sxs-lookup"><span data-stu-id="73f20-117">The following value is supported:</span></span>  
  
-   `SN_OUTFLAG_WAS_VERIFIED` <span data-ttu-id="73f20-118">(0 x 00000001) – dieser Wert wird festgelegt, um `false` um anzugeben, dass aufgrund von registrierungseinstellungen für die Überprüfung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="73f20-118">(0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="73f20-119">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="73f20-119">Return Value</span></span>  
 `S_OK` <span data-ttu-id="73f20-120">Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="73f20-120">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73f20-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="73f20-121">Requirements</span></span>  
 <span data-ttu-id="73f20-122">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73f20-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73f20-123">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="73f20-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="73f20-124">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="73f20-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="73f20-125">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="73f20-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="73f20-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73f20-126">See also</span></span>

- [<span data-ttu-id="73f20-127">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="73f20-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
