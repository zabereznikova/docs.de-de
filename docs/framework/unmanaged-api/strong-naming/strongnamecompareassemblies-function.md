---
title: StrongNameCompareAssemblies-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameCompareAssemblies
helpviewer_keywords:
- StrongNameCompareAssemblies function [.NET Framework strong naming]
ms.assetid: 763f2375-efc6-4219-8806-a3b0567ef72b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e92a59e42674c184209e9c912e9bb2ead07bdaa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54515705"
---
# <a name="strongnamecompareassemblies-function"></a><span data-ttu-id="4c35f-102">StrongNameCompareAssemblies-Funktion</span><span class="sxs-lookup"><span data-stu-id="4c35f-102">StrongNameCompareAssemblies Function</span></span>
<span data-ttu-id="4c35f-103">Bestimmt, ob sich zwei Assemblys nur durch die Signaturen ihrer starken Namen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="4c35f-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
 <span data-ttu-id="4c35f-104">Diese Funktion wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="4c35f-104">This function has been deprecated.</span></span> <span data-ttu-id="4c35f-105">Verwenden der [ICLRStrongName:: StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="4c35f-105">Use the [ICLRStrongName::StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c35f-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="4c35f-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4c35f-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="4c35f-107">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="4c35f-108">[in] Der Pfad zu die erste Assembly.</span><span class="sxs-lookup"><span data-stu-id="4c35f-108">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="4c35f-109">[in] Der Pfad für die zweite Assembly.</span><span class="sxs-lookup"><span data-stu-id="4c35f-109">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="4c35f-110">[out] Eine der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="4c35f-110">[out] One of the following values:</span></span>  
  
-   <span data-ttu-id="4c35f-111">`SN_CMP_DIFFERENT` (0): Gibt an, dass die Assemblys mit unterschiedliche Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="4c35f-111">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
-   <span data-ttu-id="4c35f-112">`SN_CMP_IDENTICAL` (1) – gibt an, dass die Assemblys identisch, einschließlich ihrer Signaturen und die Prüfsumme sind.</span><span class="sxs-lookup"><span data-stu-id="4c35f-112">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
-   <span data-ttu-id="4c35f-113">`SN_CMP_SIGONLY` (2): Gibt an, dass die Assemblys nur durch die Signatur und der Prüfsumme unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="4c35f-113">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4c35f-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4c35f-114">Return Value</span></span>  
 <span data-ttu-id="4c35f-115">`true` Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="4c35f-115">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c35f-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4c35f-116">Requirements</span></span>  
 <span data-ttu-id="4c35f-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c35f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c35f-118">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="4c35f-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="4c35f-119">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4c35f-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4c35f-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c35f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c35f-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4c35f-121">Remarks</span></span>  
 <span data-ttu-id="4c35f-122">Die Signatur einer Assembly mit starkem Namen bestehen Textnamen, Version, Kultur und öffentliches Schlüsseltoken der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="4c35f-122">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
 <span data-ttu-id="4c35f-123">Wenn die `StrongNameCompareAssemblies` Funktion nicht erfolgreich abgeschlossen wurde, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4c35f-123">If the `StrongNameCompareAssemblies` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c35f-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c35f-124">See also</span></span>
- [<span data-ttu-id="4c35f-125">StrongNameCompareAssemblies-Methode</span><span class="sxs-lookup"><span data-stu-id="4c35f-125">StrongNameCompareAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md)
- [<span data-ttu-id="4c35f-126">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4c35f-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
