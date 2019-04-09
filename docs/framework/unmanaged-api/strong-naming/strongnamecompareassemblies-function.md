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
ms.openlocfilehash: 2a49252d00f75b4d0b6325aeae0aab22f8ada5e4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191379"
---
# <a name="strongnamecompareassemblies-function"></a><span data-ttu-id="8db51-102">StrongNameCompareAssemblies-Funktion</span><span class="sxs-lookup"><span data-stu-id="8db51-102">StrongNameCompareAssemblies Function</span></span>
<span data-ttu-id="8db51-103">Bestimmt, ob sich zwei Assemblys nur durch die Signaturen ihrer starken Namen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="8db51-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
 <span data-ttu-id="8db51-104">Diese Funktion wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="8db51-104">This function has been deprecated.</span></span> <span data-ttu-id="8db51-105">Verwenden der [ICLRStrongName:: StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="8db51-105">Use the [ICLRStrongName::StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8db51-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="8db51-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8db51-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="8db51-107">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="8db51-108">[in] Der Pfad zu die erste Assembly.</span><span class="sxs-lookup"><span data-stu-id="8db51-108">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="8db51-109">[in] Der Pfad für die zweite Assembly.</span><span class="sxs-lookup"><span data-stu-id="8db51-109">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="8db51-110">[out] Eine der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="8db51-110">[out] One of the following values:</span></span>  
  
-   `SN_CMP_DIFFERENT` <span data-ttu-id="8db51-111">(0): Gibt an, dass die Assemblys mit unterschiedliche Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="8db51-111">(0) - Specifies that the assemblies contain different data.</span></span>  
  
-   `SN_CMP_IDENTICAL` <span data-ttu-id="8db51-112">(1) – gibt an, dass die Assemblys identisch, einschließlich ihrer Signaturen und die Prüfsumme sind.</span><span class="sxs-lookup"><span data-stu-id="8db51-112">(1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
-   `SN_CMP_SIGONLY` <span data-ttu-id="8db51-113">(2): Gibt an, dass die Assemblys nur durch die Signatur und der Prüfsumme unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="8db51-113">(2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8db51-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8db51-114">Return Value</span></span>  
 `true` <span data-ttu-id="8db51-115">Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="8db51-115">on successful completion; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8db51-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8db51-116">Requirements</span></span>  
 <span data-ttu-id="8db51-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8db51-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8db51-118">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="8db51-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="8db51-119">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8db51-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="8db51-120">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="8db51-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="remarks"></a><span data-ttu-id="8db51-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8db51-121">Remarks</span></span>  
 <span data-ttu-id="8db51-122">Die Signatur einer Assembly mit starkem Namen bestehen Textnamen, Version, Kultur und öffentliches Schlüsseltoken der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="8db51-122">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
 <span data-ttu-id="8db51-123">Wenn die `StrongNameCompareAssemblies` Funktion nicht erfolgreich abgeschlossen wurde, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8db51-123">If the `StrongNameCompareAssemblies` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8db51-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8db51-124">See also</span></span>

- [<span data-ttu-id="8db51-125">StrongNameCompareAssemblies-Methode</span><span class="sxs-lookup"><span data-stu-id="8db51-125">StrongNameCompareAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md)
- [<span data-ttu-id="8db51-126">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8db51-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
