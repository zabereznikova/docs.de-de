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
ms.openlocfilehash: 2b209e568b1e65ed785155d045cd48d1248672da
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59209800"
---
# <a name="iclrassemblyidentitymanager-interface"></a><span data-ttu-id="c6ff3-102">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6ff3-102">ICLRAssemblyIdentityManager Interface</span></span>
<span data-ttu-id="c6ff3-103">Enthält Methoden, die Kommunikation zwischen dem Host und die common Language Runtime (CLR) zu Assemblys zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c6ff3-103">Provides methods that support communication between the host and the common language runtime (CLR) about assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c6ff3-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="c6ff3-104">Methods</span></span>  
  
|<span data-ttu-id="c6ff3-105">Methode</span><span class="sxs-lookup"><span data-stu-id="c6ff3-105">Method</span></span>|<span data-ttu-id="c6ff3-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c6ff3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c6ff3-107">GetBindingIdentityFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="c6ff3-107">GetBindingIdentityFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|<span data-ttu-id="c6ff3-108">Ruft die Identität der Assembly Binden von Daten für die Assembly im angegebenen Dateipfad ab.</span><span class="sxs-lookup"><span data-stu-id="c6ff3-108">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="c6ff3-109">GetBindingIdentityFromStream-Methode</span><span class="sxs-lookup"><span data-stu-id="c6ff3-109">GetBindingIdentityFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|<span data-ttu-id="c6ff3-110">Ruft die kanonische Assemblyidentitätsdaten für die Assembly im angegebenen Stream.</span><span class="sxs-lookup"><span data-stu-id="c6ff3-110">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="c6ff3-111">GetCLRAssemblyReferenceList-Methode</span><span class="sxs-lookup"><span data-stu-id="c6ff3-111">GetCLRAssemblyReferenceList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|<span data-ttu-id="c6ff3-112">Ruft eine [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) Instanz aus der angegebenen Liste von partiellen Assemblyidentitäten.</span><span class="sxs-lookup"><span data-stu-id="c6ff3-112">Gets an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>|  
|[<span data-ttu-id="c6ff3-113">GetProbingAssembliesFromReference-Methode</span><span class="sxs-lookup"><span data-stu-id="c6ff3-113">GetProbingAssembliesFromReference Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|<span data-ttu-id="c6ff3-114">Ruft eine [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) Enumerator für die Assemblyidentitäten aus, auf die verwiesen wird durch die Assembly mit der angegebenen Identität.</span><span class="sxs-lookup"><span data-stu-id="c6ff3-114">Gets an [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity.</span></span>|  
|[<span data-ttu-id="c6ff3-115">GetReferencedAssembliesFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="c6ff3-115">GetReferencedAssembliesFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|<span data-ttu-id="c6ff3-116">Ruft eine [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) Instanz, die eine Liste der Assemblys, die auf die verwiesen wird von der Assembly in den angegebenen Dateipfad enthält.</span><span class="sxs-lookup"><span data-stu-id="c6ff3-116">Gets an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="c6ff3-117">GetReferencedAssembliesFromStream-Methode</span><span class="sxs-lookup"><span data-stu-id="c6ff3-117">GetReferencedAssembliesFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|<span data-ttu-id="c6ff3-118">Ruft einen Zeiger auf ein `ICLRReferenceAssemblyEnum` -Objekt, das Assembly für die Assemblys, auf die verwiesen wird durch die Assembly im angegebenen Stream enthält.</span><span class="sxs-lookup"><span data-stu-id="c6ff3-118">Gets a pointer to an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="c6ff3-119">IsStronglyNamed-Methode</span><span class="sxs-lookup"><span data-stu-id="c6ff3-119">IsStronglyNamed Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-isstronglynamed-method.md)|<span data-ttu-id="c6ff3-120">Ruft einen Wert, der angibt, ob die angegebene Assembly stark benannt wird.</span><span class="sxs-lookup"><span data-stu-id="c6ff3-120">Gets a value that indicates whether the specified assembly is strongly named.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6ff3-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c6ff3-121">Remarks</span></span>  
 <span data-ttu-id="c6ff3-122">Verwendung `ICLRAssemblyIdentityManager` zum Abrufen von Instanzen der `ICLRAssemblyReferenceList` und Assemblyidentitäten aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="c6ff3-122">Use `ICLRAssemblyIdentityManager` to get instances of `ICLRAssemblyReferenceList` and to enumerate assembly identities.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6ff3-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c6ff3-123">Requirements</span></span>  
 <span data-ttu-id="c6ff3-124">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6ff3-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6ff3-125">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c6ff3-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c6ff3-126">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c6ff3-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="c6ff3-127">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="c6ff3-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c6ff3-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6ff3-128">See also</span></span>

- [<span data-ttu-id="c6ff3-129">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6ff3-129">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="c6ff3-130">ICLRProbingAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6ff3-130">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="c6ff3-131">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c6ff3-131">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
