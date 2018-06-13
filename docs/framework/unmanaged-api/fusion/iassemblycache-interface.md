---
title: IAssemblyCache-Schnittstelle
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4302a73f9f077c2e1bf4f66c2b80ab025ae4a62c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430582"
---
# <a name="iassemblycache-interface"></a><span data-ttu-id="9151e-102">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9151e-102">IAssemblyCache Interface</span></span>
<span data-ttu-id="9151e-103">Stellt den globalen Assemblycache für die Verwendung durch die Fusion-Technologie dar.</span><span class="sxs-lookup"><span data-stu-id="9151e-103">Represents the global assembly cache for use by the fusion technology.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9151e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="9151e-104">Methods</span></span>  
  
|<span data-ttu-id="9151e-105">Methode</span><span class="sxs-lookup"><span data-stu-id="9151e-105">Method</span></span>|<span data-ttu-id="9151e-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9151e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9151e-107">CreateAssemblyCacheItem-Methode</span><span class="sxs-lookup"><span data-stu-id="9151e-107">CreateAssemblyCacheItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblycacheitem-method.md)|<span data-ttu-id="9151e-108">Ruft einen Verweis auf ein neues [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).</span><span class="sxs-lookup"><span data-stu-id="9151e-108">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).</span></span>|  
|[<span data-ttu-id="9151e-109">CreateAssemblyScavenger-Methode</span><span class="sxs-lookup"><span data-stu-id="9151e-109">CreateAssemblyScavenger Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblyscavenger-method.md)|<span data-ttu-id="9151e-110">Reserviert für interne Verwendung durch die Fusion-Technologie.</span><span class="sxs-lookup"><span data-stu-id="9151e-110">Reserved for internal use by the fusion technology.</span></span>|  
|[<span data-ttu-id="9151e-111">InstallAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="9151e-111">InstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-installassembly-method.md)|<span data-ttu-id="9151e-112">Wird die angegebene Assembly im globalen Assemblycache installiert.</span><span class="sxs-lookup"><span data-stu-id="9151e-112">Installs the specified assembly in the global assembly cache.</span></span>|  
|[<span data-ttu-id="9151e-113">QueryAssemblyInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="9151e-113">QueryAssemblyInfo Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-queryassemblyinfo-method.md)|<span data-ttu-id="9151e-114">Ruft die angeforderten Daten über die angegebene Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="9151e-114">Gets the requested data about the specified assembly.</span></span>|  
|[<span data-ttu-id="9151e-115">UninstallAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="9151e-115">UninstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-uninstallassembly-method.md)|<span data-ttu-id="9151e-116">Wird die angegebene Assembly aus dem globalen Assemblycache deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="9151e-116">Uninstalls the specified assembly from the global assembly cache.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9151e-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9151e-117">Requirements</span></span>  
 <span data-ttu-id="9151e-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9151e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9151e-119">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="9151e-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="9151e-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9151e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9151e-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9151e-121">See Also</span></span>  
 [<span data-ttu-id="9151e-122">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9151e-122">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="9151e-123">Globaler Assemblycache</span><span class="sxs-lookup"><span data-stu-id="9151e-123">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
