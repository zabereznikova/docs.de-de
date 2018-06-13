---
title: IAssemblyCache::InstallAssembly-Methode
ms.date: 03/30/2017
api_name:
- IAssemblyCache.InstallAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::InstallAssembly
helpviewer_keywords:
- InstallAssembly method [.NET Framework fusion]
- IAssemblyCache::InstallAssembly method [.NET Framework fusion]
ms.assetid: 33c1d269-c85e-4cb1-b0e6-1c510c8fb5fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 726a4ed8ee3d451687e0af671d948eb7648f7f58
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430023"
---
# <a name="iassemblycacheinstallassembly-method"></a><span data-ttu-id="51259-102">IAssemblyCache::InstallAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="51259-102">IAssemblyCache::InstallAssembly Method</span></span>
<span data-ttu-id="51259-103">Wird die angegebene Assembly im globalen Assemblycache installiert.</span><span class="sxs-lookup"><span data-stu-id="51259-103">Installs the specified assembly in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51259-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="51259-104">Syntax</span></span>  
  
```  
HRESULT InstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszManifestFilePath,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="51259-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="51259-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="51259-106">[in] Flags, die in Fusion.idl definiert sind.</span><span class="sxs-lookup"><span data-stu-id="51259-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="51259-107">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="51259-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="51259-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0 X 00000001)</span><span class="sxs-lookup"><span data-stu-id="51259-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
-   <span data-ttu-id="51259-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0 X 00000002)</span><span class="sxs-lookup"><span data-stu-id="51259-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pszManifestFilePath`  
 <span data-ttu-id="51259-110">[in] Der Pfad, der dem Manifest für die Assembly installieren.</span><span class="sxs-lookup"><span data-stu-id="51259-110">[in] The path to the manifest for the assembly to install.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="51259-111">[in] Ein [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) -Struktur, die Daten für die Installation enthält.</span><span class="sxs-lookup"><span data-stu-id="51259-111">[in] A [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure that contains data for the installation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51259-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="51259-112">Requirements</span></span>  
 <span data-ttu-id="51259-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51259-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51259-114">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="51259-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="51259-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51259-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51259-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51259-116">See Also</span></span>  
 [<span data-ttu-id="51259-117">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="51259-117">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
