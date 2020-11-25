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
ms.openlocfilehash: b417377ea1d0746e563490d87cc9a988e857d943
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697037"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a><span data-ttu-id="f190a-102">IAssemblyCache::CreateAssemblyCacheItem-Methode</span><span class="sxs-lookup"><span data-stu-id="f190a-102">IAssemblyCache::CreateAssemblyCacheItem Method</span></span>

<span data-ttu-id="f190a-103">Ruft einen Verweis auf ein neues [IAssemblyCacheItem](iassemblycacheitem-interface.md) -Objekt ab.</span><span class="sxs-lookup"><span data-stu-id="f190a-103">Gets a reference to a new [IAssemblyCacheItem](iassemblycacheitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f190a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f190a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f190a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f190a-105">Parameters</span></span>  

 `dwFlags`  
 <span data-ttu-id="f190a-106">in In Fusion. idl definierte Flags.</span><span class="sxs-lookup"><span data-stu-id="f190a-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="f190a-107">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="f190a-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="f190a-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="f190a-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
- <span data-ttu-id="f190a-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="f190a-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="f190a-110">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="f190a-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="f190a-111">`pvReserved` muss ein NULL-Verweis sein.</span><span class="sxs-lookup"><span data-stu-id="f190a-111">`pvReserved` must be a null reference.</span></span>  
  
 `ppAsmItem`  
 <span data-ttu-id="f190a-112">vorgenommen Der zurückgegebene `IAssemblyCacheItem` Zeiger.</span><span class="sxs-lookup"><span data-stu-id="f190a-112">[out] The returned `IAssemblyCacheItem` pointer.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="f190a-113">[in, optional] Nicht kanonisierte, durch Trennzeichen getrennte `name=value` Paare.</span><span class="sxs-lookup"><span data-stu-id="f190a-113">[in, optional] Uncanonicalized, comma-separated `name=value` pairs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f190a-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f190a-114">Requirements</span></span>  

 <span data-ttu-id="f190a-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f190a-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f190a-116">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="f190a-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="f190a-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f190a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f190a-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f190a-118">See also</span></span>

- [<span data-ttu-id="f190a-119">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f190a-119">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="f190a-120">IAssemblyCacheItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f190a-120">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
