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
ms.openlocfilehash: 539a8edf6d7248235a6e672edc9464679a2eab82
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134498"
---
# <a name="iassemblycacheuninstallassembly-method"></a><span data-ttu-id="364c2-102">IAssemblyCache::UninstallAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="364c2-102">IAssemblyCache::UninstallAssembly Method</span></span>
<span data-ttu-id="364c2-103">Deinstalliert die angegebene Assembly aus dem globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="364c2-103">Uninstalls the specified assembly from the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="364c2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="364c2-104">Syntax</span></span>  
  
```cpp  
HRESULT UninstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData,  
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="364c2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="364c2-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="364c2-106">in In Fusion. idl definierte Flags.</span><span class="sxs-lookup"><span data-stu-id="364c2-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="364c2-107">in Der Name der zu deinstallierenden Assembly.</span><span class="sxs-lookup"><span data-stu-id="364c2-107">[in] The name of the assembly to uninstall.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="364c2-108">in Eine [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) -Struktur, die die Installationsdaten für die Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="364c2-108">[in] A [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure that contains the installation data for the assembly.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="364c2-109">[out, optional] Einer der Disposition-Werte, die in Fusion. idl definiert sind.</span><span class="sxs-lookup"><span data-stu-id="364c2-109">[out, optional] One of the disposition values defined in Fusion.idl.</span></span> <span data-ttu-id="364c2-110">Folgende Werte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="364c2-110">Possible values include the following:</span></span>  
  
- <span data-ttu-id="364c2-111">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)</span><span class="sxs-lookup"><span data-stu-id="364c2-111">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)</span></span>  
  
- <span data-ttu-id="364c2-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)</span><span class="sxs-lookup"><span data-stu-id="364c2-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)</span></span>  
  
- <span data-ttu-id="364c2-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)</span><span class="sxs-lookup"><span data-stu-id="364c2-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)</span></span>  
  
- <span data-ttu-id="364c2-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)</span><span class="sxs-lookup"><span data-stu-id="364c2-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)</span></span>  
  
- <span data-ttu-id="364c2-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)</span><span class="sxs-lookup"><span data-stu-id="364c2-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)</span></span>  
  
- <span data-ttu-id="364c2-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)</span><span class="sxs-lookup"><span data-stu-id="364c2-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="364c2-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="364c2-117">Requirements</span></span>  
 <span data-ttu-id="364c2-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="364c2-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="364c2-119">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="364c2-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="364c2-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="364c2-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="364c2-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="364c2-121">See also</span></span>

- [<span data-ttu-id="364c2-122">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="364c2-122">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
