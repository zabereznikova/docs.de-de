---
title: StrongNameCompareAssemblies-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameCompareAssemblies
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameCompareAssemblies
helpviewer_keywords: StrongNameCompareAssemblies function [.NET Framework strong naming]
ms.assetid: 763f2375-efc6-4219-8806-a3b0567ef72b
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a3453cffb5e98e3623565785ab64db4f455be981
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamecompareassemblies-function"></a><span data-ttu-id="bc3a3-102">StrongNameCompareAssemblies-Funktion</span><span class="sxs-lookup"><span data-stu-id="bc3a3-102">StrongNameCompareAssemblies Function</span></span>
<span data-ttu-id="bc3a3-103">Bestimmt, ob zwei Assemblys nur durch die Signaturen ihrer starken Namen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="bc3a3-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
 <span data-ttu-id="bc3a3-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="bc3a3-104">This function has been deprecated.</span></span> <span data-ttu-id="bc3a3-105">Verwenden der [ICLRStrongName:: StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="bc3a3-105">Use the [ICLRStrongName::StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc3a3-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="bc3a3-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bc3a3-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="bc3a3-107">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="bc3a3-108">[in] Der Pfad zur ersten Assembly.</span><span class="sxs-lookup"><span data-stu-id="bc3a3-108">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="bc3a3-109">[in] Der Pfad auf die zweite Assembly.</span><span class="sxs-lookup"><span data-stu-id="bc3a3-109">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="bc3a3-110">[out] Einer der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="bc3a3-110">[out] One of the following values:</span></span>  
  
-   <span data-ttu-id="bc3a3-111">`SN_CMP_DIFFERENT`(0) – gibt an, dass die Assemblys verschiedene Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="bc3a3-111">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
-   <span data-ttu-id="bc3a3-112">`SN_CMP_IDENTICAL`(1) – gibt an, dass die Assemblys identisch, einschließlich ihrer Signaturen und die Prüfsumme sind.</span><span class="sxs-lookup"><span data-stu-id="bc3a3-112">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
-   <span data-ttu-id="bc3a3-113">`SN_CMP_SIGONLY`(2) – gibt an, dass die Assemblys nur durch Signatur und Prüfsumme unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="bc3a3-113">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bc3a3-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bc3a3-114">Return Value</span></span>  
 <span data-ttu-id="bc3a3-115">`true`Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="bc3a3-115">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc3a3-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bc3a3-116">Requirements</span></span>  
 <span data-ttu-id="bc3a3-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc3a3-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc3a3-118">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="bc3a3-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="bc3a3-119">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="bc3a3-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bc3a3-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc3a3-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc3a3-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bc3a3-121">Remarks</span></span>  
 <span data-ttu-id="bc3a3-122">Die starke Namenssignatur einer Assembly besteht aus der Assembly aneinander gehängt Textnamen, Version, Kultur und öffentliches Schlüsseltoken.</span><span class="sxs-lookup"><span data-stu-id="bc3a3-122">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
 <span data-ttu-id="bc3a3-123">Wenn die `StrongNameCompareAssemblies` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="bc3a3-123">If the `StrongNameCompareAssemblies` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc3a3-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc3a3-124">See Also</span></span>  
 [<span data-ttu-id="bc3a3-125">StrongNameCompareAssemblies-Methode</span><span class="sxs-lookup"><span data-stu-id="bc3a3-125">StrongNameCompareAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md)  
 [<span data-ttu-id="bc3a3-126">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bc3a3-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
