---
title: ICLRStrongName::StrongNameCompareAssemblies-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameCompareAssemblies
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameCompareAssemblies
helpviewer_keywords:
- ICLRStrongName::StrongNameCompareAssemblies method [.NET Framework hosting]
- StrongNameCompareAssemblies method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: b1fb356c-72cf-4aa4-8376-f291a6d97c01
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ab69a0d0bb5894c2393e240b4f89b9a16dd98939
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a><span data-ttu-id="b319b-102">ICLRStrongName::StrongNameCompareAssemblies-Methode</span><span class="sxs-lookup"><span data-stu-id="b319b-102">ICLRStrongName::StrongNameCompareAssemblies Method</span></span>
<span data-ttu-id="b319b-103">Bestimmt, ob zwei Assemblys nur durch die Signaturen ihrer starken Namen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="b319b-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b319b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b319b-104">Syntax</span></span>  
  
```  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b319b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b319b-105">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="b319b-106">[in] Der Pfad zur ersten Assembly.</span><span class="sxs-lookup"><span data-stu-id="b319b-106">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="b319b-107">[in] Der Pfad auf die zweite Assembly.</span><span class="sxs-lookup"><span data-stu-id="b319b-107">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="b319b-108">[out] Einer der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="b319b-108">[out] One of the following values:</span></span>  
  
-   <span data-ttu-id="b319b-109">`SN_CMP_DIFFERENT`(0) – gibt an, dass die Assemblys verschiedene Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="b319b-109">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
-   <span data-ttu-id="b319b-110">`SN_CMP_IDENTICAL`(1) – gibt an, dass die Assemblys identisch, einschließlich ihrer Signaturen und die Prüfsumme sind.</span><span class="sxs-lookup"><span data-stu-id="b319b-110">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
-   <span data-ttu-id="b319b-111">`SN_CMP_SIGONLY`(2) – gibt an, dass die Assemblys nur durch Signatur und Prüfsumme unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="b319b-111">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b319b-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b319b-112">Return Value</span></span>  
 <span data-ttu-id="b319b-113">`S_OK`Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [häufig auftretende HRESULT-Werte](http://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="b319b-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b319b-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b319b-114">Requirements</span></span>  
 <span data-ttu-id="b319b-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b319b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b319b-116">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="b319b-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b319b-117">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b319b-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b319b-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b319b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b319b-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b319b-119">Remarks</span></span>  
 <span data-ttu-id="b319b-120">Die starke Namenssignatur einer Assembly besteht aus der Assembly aneinander gehängt Textnamen, Version, Kultur und öffentliches Schlüsseltoken.</span><span class="sxs-lookup"><span data-stu-id="b319b-120">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b319b-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b319b-121">See Also</span></span>  
 [<span data-ttu-id="b319b-122">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b319b-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
