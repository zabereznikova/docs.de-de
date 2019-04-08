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
ms.openlocfilehash: 9fc5f3a3d5bc5699a596bcc648a7153190c130f0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075631"
---
# <a name="iassemblycache-interface"></a><span data-ttu-id="49534-102">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49534-102">IAssemblyCache Interface</span></span>
<span data-ttu-id="49534-103">Stellt den globalen Assemblycache für die Verwendung durch die Fusion-Technologie dar.</span><span class="sxs-lookup"><span data-stu-id="49534-103">Represents the global assembly cache for use by the fusion technology.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="49534-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="49534-104">Methods</span></span>  
  
|<span data-ttu-id="49534-105">Methode</span><span class="sxs-lookup"><span data-stu-id="49534-105">Method</span></span>|<span data-ttu-id="49534-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49534-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="49534-107">CreateAssemblyCacheItem-Methode</span><span class="sxs-lookup"><span data-stu-id="49534-107">CreateAssemblyCacheItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblycacheitem-method.md)|<span data-ttu-id="49534-108">Ruft einen Verweis auf ein neues [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).</span><span class="sxs-lookup"><span data-stu-id="49534-108">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).</span></span>|  
|[<span data-ttu-id="49534-109">CreateAssemblyScavenger-Methode</span><span class="sxs-lookup"><span data-stu-id="49534-109">CreateAssemblyScavenger Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblyscavenger-method.md)|<span data-ttu-id="49534-110">Durch die Fusion-Technologie können Sie für die interne Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="49534-110">Reserved for internal use by the fusion technology.</span></span>|  
|[<span data-ttu-id="49534-111">InstallAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="49534-111">InstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-installassembly-method.md)|<span data-ttu-id="49534-112">Wird die angegebene Assembly im globalen Assemblycache installiert.</span><span class="sxs-lookup"><span data-stu-id="49534-112">Installs the specified assembly in the global assembly cache.</span></span>|  
|[<span data-ttu-id="49534-113">QueryAssemblyInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="49534-113">QueryAssemblyInfo Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-queryassemblyinfo-method.md)|<span data-ttu-id="49534-114">Ruft die angeforderten Daten über die angegebene Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="49534-114">Gets the requested data about the specified assembly.</span></span>|  
|[<span data-ttu-id="49534-115">UninstallAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="49534-115">UninstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-uninstallassembly-method.md)|<span data-ttu-id="49534-116">Deinstalliert die angegebene Assembly aus dem globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="49534-116">Uninstalls the specified assembly from the global assembly cache.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="49534-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="49534-117">Requirements</span></span>  
 <span data-ttu-id="49534-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49534-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49534-119">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="49534-119">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="49534-120">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="49534-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="49534-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49534-121">See also</span></span>

- [<span data-ttu-id="49534-122">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="49534-122">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="49534-123">Globaler Assemblycache</span><span class="sxs-lookup"><span data-stu-id="49534-123">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
