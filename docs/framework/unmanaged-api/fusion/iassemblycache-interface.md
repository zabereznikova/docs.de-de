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
ms.openlocfilehash: df4f0ba018b55202c22cb90b22b927a9c426c4ed
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696855"
---
# <a name="iassemblycache-interface"></a><span data-ttu-id="e6917-102">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e6917-102">IAssemblyCache Interface</span></span>

<span data-ttu-id="e6917-103">Stellt den globalen Assemblycache für die Verwendung durch die Fusion-Technologie dar.</span><span class="sxs-lookup"><span data-stu-id="e6917-103">Represents the global assembly cache for use by the fusion technology.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e6917-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e6917-104">Methods</span></span>  
  
|<span data-ttu-id="e6917-105">Methode</span><span class="sxs-lookup"><span data-stu-id="e6917-105">Method</span></span>|<span data-ttu-id="e6917-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e6917-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e6917-107">CreateAssemblyCacheItem-Methode</span><span class="sxs-lookup"><span data-stu-id="e6917-107">CreateAssemblyCacheItem Method</span></span>](iassemblycache-createassemblycacheitem-method.md)|<span data-ttu-id="e6917-108">Ruft einen Verweis auf ein neues [IAssemblyCacheItem](iassemblycacheitem-interface.md)-Element ab.</span><span class="sxs-lookup"><span data-stu-id="e6917-108">Gets a reference to a new [IAssemblyCacheItem](iassemblycacheitem-interface.md).</span></span>|  
|[<span data-ttu-id="e6917-109">CreateAssemblyScavenger-Methode</span><span class="sxs-lookup"><span data-stu-id="e6917-109">CreateAssemblyScavenger Method</span></span>](iassemblycache-createassemblyscavenger-method.md)|<span data-ttu-id="e6917-110">Reserviert für die interne Verwendung durch die Fusion-Technologie.</span><span class="sxs-lookup"><span data-stu-id="e6917-110">Reserved for internal use by the fusion technology.</span></span>|  
|[<span data-ttu-id="e6917-111">InstallAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="e6917-111">InstallAssembly Method</span></span>](iassemblycache-installassembly-method.md)|<span data-ttu-id="e6917-112">Installiert die angegebene Assembly im globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="e6917-112">Installs the specified assembly in the global assembly cache.</span></span>|  
|[<span data-ttu-id="e6917-113">QueryAssemblyInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="e6917-113">QueryAssemblyInfo Method</span></span>](iassemblycache-queryassemblyinfo-method.md)|<span data-ttu-id="e6917-114">Ruft die angeforderten Daten zur angegebenen Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="e6917-114">Gets the requested data about the specified assembly.</span></span>|  
|[<span data-ttu-id="e6917-115">UninstallAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="e6917-115">UninstallAssembly Method</span></span>](iassemblycache-uninstallassembly-method.md)|<span data-ttu-id="e6917-116">Deinstalliert die angegebene Assembly aus dem globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="e6917-116">Uninstalls the specified assembly from the global assembly cache.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e6917-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e6917-117">Requirements</span></span>  

 <span data-ttu-id="e6917-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6917-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6917-119">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="e6917-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e6917-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6917-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6917-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e6917-121">See also</span></span>

- [<span data-ttu-id="e6917-122">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e6917-122">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="e6917-123">Globaler Assemblycache</span><span class="sxs-lookup"><span data-stu-id="e6917-123">Global Assembly Cache</span></span>](../../app-domains/gac.md)
