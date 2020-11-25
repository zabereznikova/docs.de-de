---
title: IAssemblyCacheItem-Schnittstelle
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: ccc9387a-9f44-4f4f-bf8f-0ea6d2afa21b
topic_type:
- apiref
ms.openlocfilehash: 72922d1fd0f8ae5e59fe76c7aa50f9c52dcd5302
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719943"
---
# <a name="iassemblycacheitem-interface"></a><span data-ttu-id="141b5-102">IAssemblyCacheItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="141b5-102">IAssemblyCacheItem Interface</span></span>

<span data-ttu-id="141b5-103">Stellt eine einzelne Assembly im globalen Assemblycache dar.</span><span class="sxs-lookup"><span data-stu-id="141b5-103">Represents a single assembly in the global assembly cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="141b5-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="141b5-104">Methods</span></span>  
  
|<span data-ttu-id="141b5-105">Methode</span><span class="sxs-lookup"><span data-stu-id="141b5-105">Method</span></span>|<span data-ttu-id="141b5-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="141b5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="141b5-107">AbortItem-Methode</span><span class="sxs-lookup"><span data-stu-id="141b5-107">AbortItem Method</span></span>](iassemblycacheitem-abortitem-method.md)|<span data-ttu-id="141b5-108">Ermöglicht es der Assembly im globalen Assemblycache, Cleanupvorgänge auszuführen, bevor Sie freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="141b5-108">Allows the assembly in the global assembly cache to perform cleanup operations before it is released.</span></span>|  
|[<span data-ttu-id="141b5-109">Commit-Methode</span><span class="sxs-lookup"><span data-stu-id="141b5-109">Commit Method</span></span>](iassemblycacheitem-commit-method.md)|<span data-ttu-id="141b5-110">Führt einen Commit für den zwischengespeicherten Assemblyverweis zum</span><span class="sxs-lookup"><span data-stu-id="141b5-110">Commits the cached assembly reference to memory.</span></span>|  
|[<span data-ttu-id="141b5-111">CreateStream-Methode</span><span class="sxs-lookup"><span data-stu-id="141b5-111">CreateStream Method</span></span>](iassemblycacheitem-createstream-method.md)|<span data-ttu-id="141b5-112">Erstellt einen Stream mit dem angegebenen Namen und Format.</span><span class="sxs-lookup"><span data-stu-id="141b5-112">Creates a stream with the specified name and format.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="141b5-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="141b5-113">Requirements</span></span>  

 <span data-ttu-id="141b5-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="141b5-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="141b5-115">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="141b5-115">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="141b5-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="141b5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="141b5-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="141b5-117">See also</span></span>

- [<span data-ttu-id="141b5-118">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="141b5-118">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="141b5-119">Globaler Assemblycache</span><span class="sxs-lookup"><span data-stu-id="141b5-119">Global Assembly Cache</span></span>](../../app-domains/gac.md)
- [<span data-ttu-id="141b5-120">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="141b5-120">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
