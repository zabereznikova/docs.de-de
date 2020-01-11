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
ms.openlocfilehash: 1bfc41fdad35a7e0560d251179ea035c96aecab7
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899529"
---
# <a name="iclrstrongnamestrongnamesignatureverificationfromimage-method"></a><span data-ttu-id="3919f-102">ICLRStrongName::StrongNameSignatureVerificationFromImage-Methode</span><span class="sxs-lookup"><span data-stu-id="3919f-102">ICLRStrongName::StrongNameSignatureVerificationFromImage Method</span></span>
<span data-ttu-id="3919f-103">Überprüft, ob eine Assembly, die bereits im Speicher zugeordnet wurde, für den zugehörigen öffentlichen Schlüssel gültig ist.</span><span class="sxs-lookup"><span data-stu-id="3919f-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3919f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3919f-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3919f-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="3919f-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="3919f-106">in Die relative virtuelle Adresse des zugeordneten Assemblymanifests.</span><span class="sxs-lookup"><span data-stu-id="3919f-106">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="3919f-107">in Die Größe (in Bytes) des zugeordneten Bilds.</span><span class="sxs-lookup"><span data-stu-id="3919f-107">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="3919f-108">in Flags, die das Überprüfungs Verhalten beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="3919f-108">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="3919f-109">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="3919f-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="3919f-110">`SN_INFLAG_FORCE_VER` (0x00000001): erzwingt die Überprüfung, auch wenn es erforderlich ist, Registrierungs Einstellungen zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="3919f-110">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="3919f-111">`SN_INFLAG_INSTALL` (0x00000002): gibt an, dass es sich hierbei um die erste Überprüfung für dieses Image handelt.</span><span class="sxs-lookup"><span data-stu-id="3919f-111">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
- <span data-ttu-id="3919f-112">`SN_INFLAG_ADMIN_ACCESS` (0x00000004): gibt an, dass der Cache nur Benutzern mit Administratorrechten den Zugriff gestattet.</span><span class="sxs-lookup"><span data-stu-id="3919f-112">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="3919f-113">`SN_INFLAG_USER_ACCESS` (0x00000008): gibt an, dass die Assembly nur für den aktuellen Benutzer zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="3919f-113">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="3919f-114">`SN_INFLAG_ALL_ACCESS` (0x00000010): gibt an, dass der Cache keine Garantien für die Zugriffsbeschränkung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="3919f-114">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="3919f-115">`SN_INFLAG_RUNTIME` (0x80000000): reserviert für das interne Debuggen.</span><span class="sxs-lookup"><span data-stu-id="3919f-115">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="3919f-116">vorgenommen Ein Flag für zusätzliche Ausgabeinformationen.</span><span class="sxs-lookup"><span data-stu-id="3919f-116">[out] A flag for additional output information.</span></span> <span data-ttu-id="3919f-117">Der folgende Wert wird unterstützt:</span><span class="sxs-lookup"><span data-stu-id="3919f-117">The following value is supported:</span></span>  
  
- <span data-ttu-id="3919f-118">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001): dieser Wert wird auf `false` festgelegt, um anzugeben, dass die Überprüfung aufgrund von Registrierungs Einstellungen erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="3919f-118">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3919f-119">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3919f-119">Return Value</span></span>  
 <span data-ttu-id="3919f-120">`S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="3919f-120">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3919f-121">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3919f-121">Requirements</span></span>  
 <span data-ttu-id="3919f-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3919f-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3919f-123">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="3919f-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3919f-124">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3919f-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3919f-125">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3919f-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3919f-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3919f-126">See also</span></span>

- [<span data-ttu-id="3919f-127">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3919f-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
