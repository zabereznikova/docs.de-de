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
ms.openlocfilehash: 134b32b6b281a08997849f4c23edfc1f357dadcd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674397"
---
# <a name="iclrstrongnamestrongnamesignatureverificationfromimage-method"></a><span data-ttu-id="34c20-102">ICLRStrongName::StrongNameSignatureVerificationFromImage-Methode</span><span class="sxs-lookup"><span data-stu-id="34c20-102">ICLRStrongName::StrongNameSignatureVerificationFromImage Method</span></span>

<span data-ttu-id="34c20-103">Überprüft, ob eine Assembly, die bereits im Speicher zugeordnet wurde, für den zugehörigen öffentlichen Schlüssel gültig ist.</span><span class="sxs-lookup"><span data-stu-id="34c20-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34c20-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="34c20-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34c20-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="34c20-105">Parameters</span></span>  

 `pbBase`  
 <span data-ttu-id="34c20-106">in Die relative virtuelle Adresse des zugeordneten Assemblymanifests.</span><span class="sxs-lookup"><span data-stu-id="34c20-106">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="34c20-107">in Die Größe (in Bytes) des zugeordneten Bilds.</span><span class="sxs-lookup"><span data-stu-id="34c20-107">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="34c20-108">in Flags, die das Überprüfungs Verhalten beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="34c20-108">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="34c20-109">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="34c20-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="34c20-110">`SN_INFLAG_FORCE_VER` (0x00000001): erzwingt die Überprüfung, auch wenn es erforderlich ist, Registrierungs Einstellungen zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="34c20-110">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="34c20-111">`SN_INFLAG_INSTALL` (0x00000002): gibt an, dass dies die erste Überprüfung für dieses Bild ist.</span><span class="sxs-lookup"><span data-stu-id="34c20-111">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
- <span data-ttu-id="34c20-112">`SN_INFLAG_ADMIN_ACCESS` (0x00000004): gibt an, dass der Cache nur Benutzern mit Administratorrechten Zugriff gestattet.</span><span class="sxs-lookup"><span data-stu-id="34c20-112">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="34c20-113">`SN_INFLAG_USER_ACCESS` (0x00000008): gibt an, dass die Assembly nur für den aktuellen Benutzer zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="34c20-113">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="34c20-114">`SN_INFLAG_ALL_ACCESS` (0x00000010): gibt an, dass der Cache keine Garantien für die Zugriffsbeschränkung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="34c20-114">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="34c20-115">`SN_INFLAG_RUNTIME` (0x80000000): reserviert für das interne Debuggen.</span><span class="sxs-lookup"><span data-stu-id="34c20-115">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="34c20-116">vorgenommen Ein Flag für zusätzliche Ausgabeinformationen.</span><span class="sxs-lookup"><span data-stu-id="34c20-116">[out] A flag for additional output information.</span></span> <span data-ttu-id="34c20-117">Der folgende Wert wird unterstützt:</span><span class="sxs-lookup"><span data-stu-id="34c20-117">The following value is supported:</span></span>  
  
- <span data-ttu-id="34c20-118">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001): dieser Wert wird auf festgelegt, `false` um anzugeben, dass die Überprüfung aufgrund von Registrierungs Einstellungen erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="34c20-118">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="34c20-119">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="34c20-119">Return Value</span></span>  

 <span data-ttu-id="34c20-120">`S_OK` , wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="34c20-120">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34c20-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="34c20-121">Requirements</span></span>  

 <span data-ttu-id="34c20-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34c20-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34c20-123">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="34c20-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="34c20-124">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="34c20-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="34c20-125">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34c20-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34c20-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="34c20-126">See also</span></span>

- [<span data-ttu-id="34c20-127">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="34c20-127">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
