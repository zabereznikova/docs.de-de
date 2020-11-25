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
ms.openlocfilehash: b90cc6fe99cf592f1b3fd117888462a957e4ce35
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708425"
---
# <a name="strongnamesignatureverificationfromimage-function"></a><span data-ttu-id="0e6b2-102">StrongNameSignatureVerificationFromImage-Funktion</span><span class="sxs-lookup"><span data-stu-id="0e6b2-102">StrongNameSignatureVerificationFromImage Function</span></span>

<span data-ttu-id="0e6b2-103">Überprüft, ob eine Assembly, die bereits im Speicher zugeordnet wurde, für den zugehörigen öffentlichen Schlüssel gültig ist.</span><span class="sxs-lookup"><span data-stu-id="0e6b2-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
 <span data-ttu-id="0e6b2-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="0e6b2-104">This function has been deprecated.</span></span> <span data-ttu-id="0e6b2-105">Verwenden Sie stattdessen die [ICLRStrongName:: strongnameverificationfromimage](../hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="0e6b2-105">Use the [ICLRStrongName::StrongNameVerificationFromImage](../hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e6b2-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e6b2-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e6b2-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="0e6b2-107">Parameters</span></span>  

 `pbBase`  
 <span data-ttu-id="0e6b2-108">in Die relative virtuelle Adresse des zugeordneten Assemblymanifests.</span><span class="sxs-lookup"><span data-stu-id="0e6b2-108">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="0e6b2-109">in Die Größe (in Bytes) des zugeordneten Bilds.</span><span class="sxs-lookup"><span data-stu-id="0e6b2-109">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="0e6b2-110">in Flags, die das Überprüfungs Verhalten beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="0e6b2-110">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="0e6b2-111">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="0e6b2-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="0e6b2-112">`SN_INFLAG_FORCE_VER` (0x00000001): erzwingt die Überprüfung, auch wenn es erforderlich ist, Registrierungs Einstellungen zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="0e6b2-112">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="0e6b2-113">`SN_INFLAG_INSTALL` (0x00000002): gibt an, dass dies die erste Überprüfung für dieses Bild ist.</span><span class="sxs-lookup"><span data-stu-id="0e6b2-113">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
- <span data-ttu-id="0e6b2-114">`SN_INFLAG_ADMIN_ACCESS` (0x00000004): gibt an, dass der Cache nur Benutzern mit Administratorrechten Zugriff gestattet.</span><span class="sxs-lookup"><span data-stu-id="0e6b2-114">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="0e6b2-115">`SN_INFLAG_USER_ACCESS` (0x00000008): gibt an, dass die Assembly nur für den aktuellen Benutzer zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="0e6b2-115">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="0e6b2-116">`SN_INFLAG_ALL_ACCESS` (0x00000010): gibt an, dass der Cache keine Garantien für die Zugriffsbeschränkung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="0e6b2-116">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="0e6b2-117">`SN_INFLAG_RUNTIME` (0x80000000): reserviert für das interne Debuggen.</span><span class="sxs-lookup"><span data-stu-id="0e6b2-117">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="0e6b2-118">vorgenommen Ein Flag für zusätzliche Ausgabeinformationen.</span><span class="sxs-lookup"><span data-stu-id="0e6b2-118">[out] A flag for additional output information.</span></span> <span data-ttu-id="0e6b2-119">Der folgende Wert wird unterstützt:</span><span class="sxs-lookup"><span data-stu-id="0e6b2-119">The following value is supported:</span></span>  
  
- <span data-ttu-id="0e6b2-120">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001): dieser Wert wird auf festgelegt, `false` um anzugeben, dass die Überprüfung aufgrund von Registrierungs Einstellungen erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="0e6b2-120">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0e6b2-121">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0e6b2-121">Return Value</span></span>  

 <span data-ttu-id="0e6b2-122">`true` nach erfolgreichem Abschluss: andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="0e6b2-122">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e6b2-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0e6b2-123">Remarks</span></span>  

 <span data-ttu-id="0e6b2-124">Wenn die `StrongNameSignatureVerificationFromImage` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0e6b2-124">If the `StrongNameSignatureVerificationFromImage` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e6b2-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0e6b2-125">Requirements</span></span>  

 <span data-ttu-id="0e6b2-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e6b2-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e6b2-127">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="0e6b2-127">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="0e6b2-128">**Bibliothek:** Als Ressource in mscoree.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0e6b2-128">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="0e6b2-129">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e6b2-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e6b2-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0e6b2-130">See also</span></span>

- [<span data-ttu-id="0e6b2-131">StrongNameSignatureVerificationFromImage-Methode</span><span class="sxs-lookup"><span data-stu-id="0e6b2-131">StrongNameSignatureVerificationFromImage Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)
- [<span data-ttu-id="0e6b2-132">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0e6b2-132">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
