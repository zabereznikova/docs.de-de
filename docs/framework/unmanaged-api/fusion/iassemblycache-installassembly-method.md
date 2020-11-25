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
ms.openlocfilehash: 230b904dd1cca1a1289713e3df7a709bd1c3a22b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696896"
---
# <a name="iassemblycacheinstallassembly-method"></a><span data-ttu-id="c7bbe-102">IAssemblyCache::InstallAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="c7bbe-102">IAssemblyCache::InstallAssembly Method</span></span>

<span data-ttu-id="c7bbe-103">Installiert die angegebene Assembly im globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="c7bbe-103">Installs the specified assembly in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7bbe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7bbe-104">Syntax</span></span>  
  
```cpp  
HRESULT InstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszManifestFilePath,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7bbe-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c7bbe-105">Parameters</span></span>  

 `dwFlags`  
 <span data-ttu-id="c7bbe-106">in In Fusion. idl definierte Flags.</span><span class="sxs-lookup"><span data-stu-id="c7bbe-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="c7bbe-107">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="c7bbe-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="c7bbe-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="c7bbe-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
- <span data-ttu-id="c7bbe-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="c7bbe-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pszManifestFilePath`  
 <span data-ttu-id="c7bbe-110">in Der Pfad zum Manifest für die zu installier-Assembly.</span><span class="sxs-lookup"><span data-stu-id="c7bbe-110">[in] The path to the manifest for the assembly to install.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="c7bbe-111">in Eine [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) -Struktur, die Daten für die Installation enthält.</span><span class="sxs-lookup"><span data-stu-id="c7bbe-111">[in] A [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure that contains data for the installation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7bbe-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c7bbe-112">Requirements</span></span>  

 <span data-ttu-id="c7bbe-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7bbe-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7bbe-114">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="c7bbe-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c7bbe-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7bbe-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7bbe-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c7bbe-116">See also</span></span>

- [<span data-ttu-id="c7bbe-117">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c7bbe-117">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
