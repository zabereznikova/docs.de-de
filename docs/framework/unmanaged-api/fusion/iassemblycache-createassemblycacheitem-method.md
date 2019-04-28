---
title: IAssemblyCache::CreateAssemblyCacheItem-Methode
ms.date: 03/30/2017
api_name:
- IAssemblyCache.CreateAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::CreateAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCache::CreateAssemblyCacheItem method [.NET Framework fusion]
- CreateAssemblyCacheItem method [.NET Framework fusion]
ms.assetid: 017a7ba5-aaaf-44e2-9cbe-ceebef259df0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 648b641cbd2ec97305674451df06ce5be6a93a49
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697640"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a><span data-ttu-id="720f8-102">IAssemblyCache::CreateAssemblyCacheItem-Methode</span><span class="sxs-lookup"><span data-stu-id="720f8-102">IAssemblyCache::CreateAssemblyCacheItem Method</span></span>
<span data-ttu-id="720f8-103">Ruft einen Verweis auf ein neues [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="720f8-103">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="720f8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="720f8-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="720f8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="720f8-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="720f8-106">[in] Flags, die in Fusion.idl definiert sind.</span><span class="sxs-lookup"><span data-stu-id="720f8-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="720f8-107">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="720f8-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="720f8-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0 X 00000001)</span><span class="sxs-lookup"><span data-stu-id="720f8-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
- <span data-ttu-id="720f8-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="720f8-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="720f8-110">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="720f8-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="720f8-111">`pvReserved` ein null-Verweis muss sein.</span><span class="sxs-lookup"><span data-stu-id="720f8-111">`pvReserved` must be a null reference.</span></span>  
  
 `ppAsmItem`  
 <span data-ttu-id="720f8-112">[out] Das zurückgegebene `IAssemblyCacheItem` Zeiger.</span><span class="sxs-lookup"><span data-stu-id="720f8-112">[out] The returned `IAssemblyCacheItem` pointer.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="720f8-113">[in, optional] Uncanonicalized, durch Trennzeichen getrennte `name=value` Paare.</span><span class="sxs-lookup"><span data-stu-id="720f8-113">[in, optional] Uncanonicalized, comma-separated `name=value` pairs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="720f8-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="720f8-114">Requirements</span></span>  
 <span data-ttu-id="720f8-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="720f8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="720f8-116">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="720f8-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="720f8-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="720f8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="720f8-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="720f8-118">See also</span></span>

- [<span data-ttu-id="720f8-119">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="720f8-119">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [<span data-ttu-id="720f8-120">IAssemblyCacheItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="720f8-120">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
