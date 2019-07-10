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
ms.openlocfilehash: cd420f0f166b0b17e5fbaf08d6bedd6651188b1c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778740"
---
# <a name="iassemblycacheinstallassembly-method"></a><span data-ttu-id="32425-102">IAssemblyCache::InstallAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="32425-102">IAssemblyCache::InstallAssembly Method</span></span>
<span data-ttu-id="32425-103">Wird die angegebene Assembly im globalen Assemblycache installiert.</span><span class="sxs-lookup"><span data-stu-id="32425-103">Installs the specified assembly in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32425-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="32425-104">Syntax</span></span>  
  
```cpp  
HRESULT InstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszManifestFilePath,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32425-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="32425-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="32425-106">[in] Flags, die in Fusion.idl definiert sind.</span><span class="sxs-lookup"><span data-stu-id="32425-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="32425-107">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="32425-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="32425-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0 X 00000001)</span><span class="sxs-lookup"><span data-stu-id="32425-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
- <span data-ttu-id="32425-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="32425-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pszManifestFilePath`  
 <span data-ttu-id="32425-110">[in] Der Pfad des Manifests für zu installierenden Assembly.</span><span class="sxs-lookup"><span data-stu-id="32425-110">[in] The path to the manifest for the assembly to install.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="32425-111">[in] Ein [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) Struktur, die Daten für die Installation enthält.</span><span class="sxs-lookup"><span data-stu-id="32425-111">[in] A [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure that contains data for the installation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32425-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="32425-112">Requirements</span></span>  
 <span data-ttu-id="32425-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32425-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32425-114">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="32425-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="32425-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32425-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32425-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32425-116">See also</span></span>

- [<span data-ttu-id="32425-117">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="32425-117">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
