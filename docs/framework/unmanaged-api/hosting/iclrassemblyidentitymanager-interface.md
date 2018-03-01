---
title: ICLRAssemblyIdentityManager-Schnittstelle
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
- ICLRAssemblyIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager
helpviewer_keywords:
- ICLRAssemblyIdentityManager interface [.NET Framework hosting]
ms.assetid: 6a81c6fe-cc22-4062-ae27-d6eeee03a7b9
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 168c67eb701d7dfc461553cfe32ed43dcea5e844
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrassemblyidentitymanager-interface"></a><span data-ttu-id="43002-102">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43002-102">ICLRAssemblyIdentityManager Interface</span></span>
<span data-ttu-id="43002-103">Enthält Methoden, die Kommunikation zwischen dem Host und die common Language Runtime (CLR) über Assemblys zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="43002-103">Provides methods that support communication between the host and the common language runtime (CLR) about assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="43002-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="43002-104">Methods</span></span>  
  
|<span data-ttu-id="43002-105">Methode</span><span class="sxs-lookup"><span data-stu-id="43002-105">Method</span></span>|<span data-ttu-id="43002-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="43002-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="43002-107">GetBindingIdentityFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="43002-107">GetBindingIdentityFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|<span data-ttu-id="43002-108">Ruft die Identität der Assembly Binden von Daten für die Assembly im angegebenen Dateipfad ab.</span><span class="sxs-lookup"><span data-stu-id="43002-108">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="43002-109">GetBindingIdentityFromStream-Methode</span><span class="sxs-lookup"><span data-stu-id="43002-109">GetBindingIdentityFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|<span data-ttu-id="43002-110">Ruft die Identitätsdaten kanonische Assembly für die Assembly im angegebenen Stream.</span><span class="sxs-lookup"><span data-stu-id="43002-110">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="43002-111">GetCLRAssemblyReferenceList-Methode</span><span class="sxs-lookup"><span data-stu-id="43002-111">GetCLRAssemblyReferenceList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|<span data-ttu-id="43002-112">Ruft eine [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) Instanz aus der angegebenen Liste von partiellen Assemblyidentitäten.</span><span class="sxs-lookup"><span data-stu-id="43002-112">Gets an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>|  
|[<span data-ttu-id="43002-113">GetProbingAssembliesFromReference-Methode</span><span class="sxs-lookup"><span data-stu-id="43002-113">GetProbingAssembliesFromReference Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|<span data-ttu-id="43002-114">Ruft eine [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) Enumerator für die Assemblyidentitäten verweist auf die Assembly mit der angegebenen Identität.</span><span class="sxs-lookup"><span data-stu-id="43002-114">Gets an [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity.</span></span>|  
|[<span data-ttu-id="43002-115">GetReferencedAssembliesFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="43002-115">GetReferencedAssembliesFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|<span data-ttu-id="43002-116">Ruft eine [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) -Instanz, eine Liste der Assemblys enthält, auf die Assembly auf der angegebene Pfad verweist.</span><span class="sxs-lookup"><span data-stu-id="43002-116">Gets an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="43002-117">GetReferencedAssembliesFromStream-Methode</span><span class="sxs-lookup"><span data-stu-id="43002-117">GetReferencedAssembliesFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|<span data-ttu-id="43002-118">Ruft einen Zeiger auf ein `ICLRReferenceAssemblyEnum` Objekt, das für die Assemblys, die von der Assembly im angegebenen Stream Assemblyidentitätsdaten enthält.</span><span class="sxs-lookup"><span data-stu-id="43002-118">Gets a pointer to an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="43002-119">IsStronglyNamed-Methode</span><span class="sxs-lookup"><span data-stu-id="43002-119">IsStronglyNamed Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-isstronglynamed-method.md)|<span data-ttu-id="43002-120">Ruft einen Wert, der angibt, ob die angegebene Assembly stark benannt wird.</span><span class="sxs-lookup"><span data-stu-id="43002-120">Gets a value that indicates whether the specified assembly is strongly named.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43002-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="43002-121">Remarks</span></span>  
 <span data-ttu-id="43002-122">Verwendung `ICLRAssemblyIdentityManager` zum Abrufen von Instanzen von `ICLRAssemblyReferenceList` und Assemblyidentitäten aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="43002-122">Use `ICLRAssemblyIdentityManager` to get instances of `ICLRAssemblyReferenceList` and to enumerate assembly identities.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43002-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="43002-123">Requirements</span></span>  
 <span data-ttu-id="43002-124">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43002-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43002-125">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="43002-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="43002-126">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="43002-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="43002-127">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43002-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43002-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43002-128">See Also</span></span>  
 [<span data-ttu-id="43002-129">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43002-129">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="43002-130">ICLRProbingAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43002-130">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 [<span data-ttu-id="43002-131">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="43002-131">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
