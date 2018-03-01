---
title: IAssemblyCache-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IAssemblyCache
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache
helpviewer_keywords:
- IAssemblyCache interface [.NET Framework fusion]
ms.assetid: 71ea170f-872d-4fc5-81b6-27da1dec9b19
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 21ebc29a6c442625f7a532f7b1e6a47e7dc4cb69
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblycache-interface"></a><span data-ttu-id="e1de9-102">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e1de9-102">IAssemblyCache Interface</span></span>
<span data-ttu-id="e1de9-103">Stellt den globalen Assemblycache für die Verwendung durch die Fusion-Technologie dar.</span><span class="sxs-lookup"><span data-stu-id="e1de9-103">Represents the global assembly cache for use by the fusion technology.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e1de9-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e1de9-104">Methods</span></span>  
  
|<span data-ttu-id="e1de9-105">Methode</span><span class="sxs-lookup"><span data-stu-id="e1de9-105">Method</span></span>|<span data-ttu-id="e1de9-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1de9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e1de9-107">CreateAssemblyCacheItem-Methode</span><span class="sxs-lookup"><span data-stu-id="e1de9-107">CreateAssemblyCacheItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblycacheitem-method.md)|<span data-ttu-id="e1de9-108">Ruft einen Verweis auf ein neues [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).</span><span class="sxs-lookup"><span data-stu-id="e1de9-108">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).</span></span>|  
|[<span data-ttu-id="e1de9-109">CreateAssemblyScavenger-Methode</span><span class="sxs-lookup"><span data-stu-id="e1de9-109">CreateAssemblyScavenger Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblyscavenger-method.md)|<span data-ttu-id="e1de9-110">Reserviert für interne Verwendung durch die Fusion-Technologie.</span><span class="sxs-lookup"><span data-stu-id="e1de9-110">Reserved for internal use by the fusion technology.</span></span>|  
|[<span data-ttu-id="e1de9-111">InstallAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="e1de9-111">InstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-installassembly-method.md)|<span data-ttu-id="e1de9-112">Wird die angegebene Assembly im globalen Assemblycache installiert.</span><span class="sxs-lookup"><span data-stu-id="e1de9-112">Installs the specified assembly in the global assembly cache.</span></span>|  
|[<span data-ttu-id="e1de9-113">QueryAssemblyInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="e1de9-113">QueryAssemblyInfo Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-queryassemblyinfo-method.md)|<span data-ttu-id="e1de9-114">Ruft die angeforderten Daten über die angegebene Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="e1de9-114">Gets the requested data about the specified assembly.</span></span>|  
|[<span data-ttu-id="e1de9-115">UninstallAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="e1de9-115">UninstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-uninstallassembly-method.md)|<span data-ttu-id="e1de9-116">Wird die angegebene Assembly aus dem globalen Assemblycache deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="e1de9-116">Uninstalls the specified assembly from the global assembly cache.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e1de9-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e1de9-117">Requirements</span></span>  
 <span data-ttu-id="e1de9-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1de9-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1de9-119">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="e1de9-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e1de9-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1de9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1de9-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1de9-121">See Also</span></span>  
 [<span data-ttu-id="e1de9-122">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e1de9-122">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="e1de9-123">Globaler Assemblycache</span><span class="sxs-lookup"><span data-stu-id="e1de9-123">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
