---
title: IAssemblyCache::UninstallAssembly-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyCache.UninstallAssembly
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyCache::UninstallAssembly
helpviewer_keywords:
- UninstallAssembly method [.NET Framework fusion]
- IAssemblyCache::UninstallAssembly method [.NET Framework fusion]
ms.assetid: 973b2c44-8dfc-40c1-9035-10f4846627e9
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d34b2793de58721c7d4863855106d4b231bccc54
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblycacheuninstallassembly-method"></a><span data-ttu-id="1ff43-102">IAssemblyCache::UninstallAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="1ff43-102">IAssemblyCache::UninstallAssembly Method</span></span>
<span data-ttu-id="1ff43-103">Wird die angegebene Assembly aus dem globalen Assemblycache deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="1ff43-103">Uninstalls the specified assembly from the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ff43-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ff43-104">Syntax</span></span>  
  
```  
HRESULT UninstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData,  
    [out, optional] ULONG *pulDisposition  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1ff43-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1ff43-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="1ff43-106">[in] Flags, die in Fusion.idl definiert sind.</span><span class="sxs-lookup"><span data-stu-id="1ff43-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="1ff43-107">[in] Der Name der Assembly zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="1ff43-107">[in] The name of the assembly to uninstall.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="1ff43-108">[in] Ein [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) -Struktur, die Installationsdaten für die Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="1ff43-108">[in] A [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure that contains the installation data for the assembly.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="1ff43-109">[out, optional] Einer der Dispositionswerte, die in Fusion.idl definiert sind.</span><span class="sxs-lookup"><span data-stu-id="1ff43-109">[out, optional] One of the disposition values defined in Fusion.idl.</span></span> <span data-ttu-id="1ff43-110">Mögliche Werte umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1ff43-110">Possible values include the following:</span></span>  
  
-   <span data-ttu-id="1ff43-111">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)</span><span class="sxs-lookup"><span data-stu-id="1ff43-111">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)</span></span>  
  
-   <span data-ttu-id="1ff43-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)</span><span class="sxs-lookup"><span data-stu-id="1ff43-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)</span></span>  
  
-   <span data-ttu-id="1ff43-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)</span><span class="sxs-lookup"><span data-stu-id="1ff43-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)</span></span>  
  
-   <span data-ttu-id="1ff43-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)</span><span class="sxs-lookup"><span data-stu-id="1ff43-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)</span></span>  
  
-   <span data-ttu-id="1ff43-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)</span><span class="sxs-lookup"><span data-stu-id="1ff43-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)</span></span>  
  
-   <span data-ttu-id="1ff43-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)</span><span class="sxs-lookup"><span data-stu-id="1ff43-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ff43-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1ff43-117">Requirements</span></span>  
 <span data-ttu-id="1ff43-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ff43-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ff43-119">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="1ff43-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="1ff43-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ff43-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ff43-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ff43-121">See Also</span></span>  
 [<span data-ttu-id="1ff43-122">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1ff43-122">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
