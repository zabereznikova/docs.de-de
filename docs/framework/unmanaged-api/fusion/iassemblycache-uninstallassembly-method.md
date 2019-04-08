---
title: IAssemblyCache::UninstallAssembly-Methode
ms.date: 03/30/2017
api_name:
- IAssemblyCache.UninstallAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::UninstallAssembly
helpviewer_keywords:
- UninstallAssembly method [.NET Framework fusion]
- IAssemblyCache::UninstallAssembly method [.NET Framework fusion]
ms.assetid: 973b2c44-8dfc-40c1-9035-10f4846627e9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75ef24162adbb653671ed070587e7155fae6b949
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079109"
---
# <a name="iassemblycacheuninstallassembly-method"></a><span data-ttu-id="e7d42-102">IAssemblyCache::UninstallAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="e7d42-102">IAssemblyCache::UninstallAssembly Method</span></span>
<span data-ttu-id="e7d42-103">Deinstalliert die angegebene Assembly aus dem globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="e7d42-103">Uninstalls the specified assembly from the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7d42-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7d42-104">Syntax</span></span>  
  
```  
HRESULT UninstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData,  
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7d42-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e7d42-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="e7d42-106">[in] Flags, die in Fusion.idl definiert sind.</span><span class="sxs-lookup"><span data-stu-id="e7d42-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="e7d42-107">[in] Der Name der zu deinstallierenden Assembly.</span><span class="sxs-lookup"><span data-stu-id="e7d42-107">[in] The name of the assembly to uninstall.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="e7d42-108">[in] Ein [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) -Struktur, die die Installationsdaten für die Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="e7d42-108">[in] A [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure that contains the installation data for the assembly.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="e7d42-109">[Out, optional] Einer der Dispositionswerte in Fusion.idl definiert sind.</span><span class="sxs-lookup"><span data-stu-id="e7d42-109">[out, optional] One of the disposition values defined in Fusion.idl.</span></span> <span data-ttu-id="e7d42-110">Die folgenden: mögliche Werten</span><span class="sxs-lookup"><span data-stu-id="e7d42-110">Possible values include the following:</span></span>  
  
-   <span data-ttu-id="e7d42-111">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)</span><span class="sxs-lookup"><span data-stu-id="e7d42-111">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)</span></span>  
  
-   <span data-ttu-id="e7d42-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)</span><span class="sxs-lookup"><span data-stu-id="e7d42-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)</span></span>  
  
-   <span data-ttu-id="e7d42-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)</span><span class="sxs-lookup"><span data-stu-id="e7d42-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)</span></span>  
  
-   <span data-ttu-id="e7d42-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)</span><span class="sxs-lookup"><span data-stu-id="e7d42-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)</span></span>  
  
-   <span data-ttu-id="e7d42-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)</span><span class="sxs-lookup"><span data-stu-id="e7d42-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)</span></span>  
  
-   <span data-ttu-id="e7d42-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)</span><span class="sxs-lookup"><span data-stu-id="e7d42-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7d42-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e7d42-117">Requirements</span></span>  
 <span data-ttu-id="e7d42-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7d42-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7d42-119">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="e7d42-119">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="e7d42-120">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="e7d42-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e7d42-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7d42-121">See also</span></span>

- [<span data-ttu-id="e7d42-122">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e7d42-122">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
