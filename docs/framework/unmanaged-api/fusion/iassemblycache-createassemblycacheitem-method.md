---
title: IAssemblyCache::CreateAssemblyCacheItem-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyCache.CreateAssemblyCacheItem
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyCache::CreateAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCache::CreateAssemblyCacheItem method [.NET Framework fusion]
- CreateAssemblyCacheItem method [.NET Framework fusion]
ms.assetid: 017a7ba5-aaaf-44e2-9cbe-ceebef259df0
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 65431425afb6a666679d29f9c1bbc9691caa0afb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a><span data-ttu-id="55aaf-102">IAssemblyCache::CreateAssemblyCacheItem-Methode</span><span class="sxs-lookup"><span data-stu-id="55aaf-102">IAssemblyCache::CreateAssemblyCacheItem Method</span></span>
<span data-ttu-id="55aaf-103">Ruft einen Verweis auf ein neues [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="55aaf-103">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55aaf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="55aaf-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="55aaf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="55aaf-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="55aaf-106">[in] Flags, die in Fusion.idl definiert sind.</span><span class="sxs-lookup"><span data-stu-id="55aaf-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="55aaf-107">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="55aaf-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="55aaf-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0 X 00000001)</span><span class="sxs-lookup"><span data-stu-id="55aaf-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
-   <span data-ttu-id="55aaf-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0 X 00000002)</span><span class="sxs-lookup"><span data-stu-id="55aaf-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="55aaf-110">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="55aaf-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="55aaf-111">`pvReserved`ein null-Verweis muss sein.</span><span class="sxs-lookup"><span data-stu-id="55aaf-111">`pvReserved` must be a null reference.</span></span>  
  
 `ppAsmItem`  
 <span data-ttu-id="55aaf-112">[out] Das zurückgegebene `IAssemblyCacheItem` Zeiger.</span><span class="sxs-lookup"><span data-stu-id="55aaf-112">[out] The returned `IAssemblyCacheItem` pointer.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="55aaf-113">[in, optional] Uncanonicalized, durch Trennzeichen getrennte `name=value` Paare.</span><span class="sxs-lookup"><span data-stu-id="55aaf-113">[in, optional] Uncanonicalized, comma-separated `name=value` pairs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55aaf-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="55aaf-114">Requirements</span></span>  
 <span data-ttu-id="55aaf-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55aaf-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55aaf-116">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="55aaf-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="55aaf-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55aaf-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55aaf-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55aaf-118">See Also</span></span>  
 [<span data-ttu-id="55aaf-119">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="55aaf-119">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 [<span data-ttu-id="55aaf-120">IAssemblyCacheItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="55aaf-120">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
