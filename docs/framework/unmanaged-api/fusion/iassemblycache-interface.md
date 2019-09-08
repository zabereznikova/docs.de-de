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
ms.openlocfilehash: 6dab5fe941fce3c23ba718906b29c80c6d257c2f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796777"
---
# <a name="iassemblycache-interface"></a><span data-ttu-id="0c6c1-102">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0c6c1-102">IAssemblyCache Interface</span></span>
<span data-ttu-id="0c6c1-103">Stellt den globalen Assemblycache für die Verwendung durch die Fusion-Technologie dar.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-103">Represents the global assembly cache for use by the fusion technology.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0c6c1-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="0c6c1-104">Methods</span></span>  
  
|<span data-ttu-id="0c6c1-105">Methode</span><span class="sxs-lookup"><span data-stu-id="0c6c1-105">Method</span></span>|<span data-ttu-id="0c6c1-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0c6c1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0c6c1-107">CreateAssemblyCacheItem-Methode</span><span class="sxs-lookup"><span data-stu-id="0c6c1-107">CreateAssemblyCacheItem Method</span></span>](iassemblycache-createassemblycacheitem-method.md)|<span data-ttu-id="0c6c1-108">Ruft einen Verweis auf ein neues [IAssemblyCacheItem](iassemblycacheitem-interface.md)-Element ab.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-108">Gets a reference to a new [IAssemblyCacheItem](iassemblycacheitem-interface.md).</span></span>|  
|[<span data-ttu-id="0c6c1-109">CreateAssemblyScavenger-Methode</span><span class="sxs-lookup"><span data-stu-id="0c6c1-109">CreateAssemblyScavenger Method</span></span>](iassemblycache-createassemblyscavenger-method.md)|<span data-ttu-id="0c6c1-110">Reserviert für die interne Verwendung durch die Fusion-Technologie.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-110">Reserved for internal use by the fusion technology.</span></span>|  
|[<span data-ttu-id="0c6c1-111">InstallAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="0c6c1-111">InstallAssembly Method</span></span>](iassemblycache-installassembly-method.md)|<span data-ttu-id="0c6c1-112">Installiert die angegebene Assembly im globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-112">Installs the specified assembly in the global assembly cache.</span></span>|  
|[<span data-ttu-id="0c6c1-113">QueryAssemblyInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="0c6c1-113">QueryAssemblyInfo Method</span></span>](iassemblycache-queryassemblyinfo-method.md)|<span data-ttu-id="0c6c1-114">Ruft die angeforderten Daten zur angegebenen Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-114">Gets the requested data about the specified assembly.</span></span>|  
|[<span data-ttu-id="0c6c1-115">UninstallAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="0c6c1-115">UninstallAssembly Method</span></span>](iassemblycache-uninstallassembly-method.md)|<span data-ttu-id="0c6c1-116">Deinstalliert die angegebene Assembly aus dem globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="0c6c1-116">Uninstalls the specified assembly from the global assembly cache.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0c6c1-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0c6c1-117">Requirements</span></span>  
 <span data-ttu-id="0c6c1-118">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c6c1-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c6c1-119">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="0c6c1-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="0c6c1-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c6c1-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c6c1-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c6c1-121">See also</span></span>

- [<span data-ttu-id="0c6c1-122">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="0c6c1-122">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="0c6c1-123">Globaler Assemblycache</span><span class="sxs-lookup"><span data-stu-id="0c6c1-123">Global Assembly Cache</span></span>](../../app-domains/gac.md)
