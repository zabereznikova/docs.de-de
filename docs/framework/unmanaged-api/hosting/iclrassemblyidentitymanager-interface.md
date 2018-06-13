---
title: ICLRAssemblyIdentityManager-Schnittstelle
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f3a58a9ec4ed9514e748ed6c8c21a404feed9560
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435666"
---
# <a name="iclrassemblyidentitymanager-interface"></a><span data-ttu-id="cfc84-102">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cfc84-102">ICLRAssemblyIdentityManager Interface</span></span>
<span data-ttu-id="cfc84-103">Enthält Methoden, die Kommunikation zwischen dem Host und die common Language Runtime (CLR) über Assemblys zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="cfc84-103">Provides methods that support communication between the host and the common language runtime (CLR) about assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cfc84-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="cfc84-104">Methods</span></span>  
  
|<span data-ttu-id="cfc84-105">Methode</span><span class="sxs-lookup"><span data-stu-id="cfc84-105">Method</span></span>|<span data-ttu-id="cfc84-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cfc84-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cfc84-107">GetBindingIdentityFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="cfc84-107">GetBindingIdentityFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|<span data-ttu-id="cfc84-108">Ruft die Identität der Assembly Binden von Daten für die Assembly im angegebenen Dateipfad ab.</span><span class="sxs-lookup"><span data-stu-id="cfc84-108">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="cfc84-109">GetBindingIdentityFromStream-Methode</span><span class="sxs-lookup"><span data-stu-id="cfc84-109">GetBindingIdentityFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|<span data-ttu-id="cfc84-110">Ruft die Identitätsdaten kanonische Assembly für die Assembly im angegebenen Stream.</span><span class="sxs-lookup"><span data-stu-id="cfc84-110">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="cfc84-111">GetCLRAssemblyReferenceList-Methode</span><span class="sxs-lookup"><span data-stu-id="cfc84-111">GetCLRAssemblyReferenceList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|<span data-ttu-id="cfc84-112">Ruft eine [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) Instanz aus der angegebenen Liste von partiellen Assemblyidentitäten.</span><span class="sxs-lookup"><span data-stu-id="cfc84-112">Gets an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>|  
|[<span data-ttu-id="cfc84-113">GetProbingAssembliesFromReference-Methode</span><span class="sxs-lookup"><span data-stu-id="cfc84-113">GetProbingAssembliesFromReference Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|<span data-ttu-id="cfc84-114">Ruft eine [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) Enumerator für die Assemblyidentitäten verweist auf die Assembly mit der angegebenen Identität.</span><span class="sxs-lookup"><span data-stu-id="cfc84-114">Gets an [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity.</span></span>|  
|[<span data-ttu-id="cfc84-115">GetReferencedAssembliesFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="cfc84-115">GetReferencedAssembliesFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|<span data-ttu-id="cfc84-116">Ruft eine [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) -Instanz, eine Liste der Assemblys enthält, auf die Assembly auf der angegebene Pfad verweist.</span><span class="sxs-lookup"><span data-stu-id="cfc84-116">Gets an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="cfc84-117">GetReferencedAssembliesFromStream-Methode</span><span class="sxs-lookup"><span data-stu-id="cfc84-117">GetReferencedAssembliesFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|<span data-ttu-id="cfc84-118">Ruft einen Zeiger auf ein `ICLRReferenceAssemblyEnum` Objekt, das für die Assemblys, die von der Assembly im angegebenen Stream Assemblyidentitätsdaten enthält.</span><span class="sxs-lookup"><span data-stu-id="cfc84-118">Gets a pointer to an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="cfc84-119">IsStronglyNamed-Methode</span><span class="sxs-lookup"><span data-stu-id="cfc84-119">IsStronglyNamed Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-isstronglynamed-method.md)|<span data-ttu-id="cfc84-120">Ruft einen Wert, der angibt, ob die angegebene Assembly stark benannt wird.</span><span class="sxs-lookup"><span data-stu-id="cfc84-120">Gets a value that indicates whether the specified assembly is strongly named.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cfc84-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cfc84-121">Remarks</span></span>  
 <span data-ttu-id="cfc84-122">Verwendung `ICLRAssemblyIdentityManager` zum Abrufen von Instanzen von `ICLRAssemblyReferenceList` und Assemblyidentitäten aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="cfc84-122">Use `ICLRAssemblyIdentityManager` to get instances of `ICLRAssemblyReferenceList` and to enumerate assembly identities.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfc84-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cfc84-123">Requirements</span></span>  
 <span data-ttu-id="cfc84-124">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfc84-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfc84-125">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cfc84-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cfc84-126">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="cfc84-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cfc84-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfc84-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfc84-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cfc84-128">See Also</span></span>  
 [<span data-ttu-id="cfc84-129">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cfc84-129">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="cfc84-130">ICLRProbingAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cfc84-130">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 [<span data-ttu-id="cfc84-131">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="cfc84-131">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
