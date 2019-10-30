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
ms.openlocfilehash: 26de2ebf1364981d8b8f1fb38c8fa1045191114f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126623"
---
# <a name="iclrassemblyidentitymanager-interface"></a><span data-ttu-id="c1ddb-102">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1ddb-102">ICLRAssemblyIdentityManager Interface</span></span>
<span data-ttu-id="c1ddb-103">Stellt Methoden bereit, die die Kommunikation zwischen dem Host und dem Common Language Runtime (CLR) über Assemblys unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c1ddb-103">Provides methods that support communication between the host and the common language runtime (CLR) about assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c1ddb-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="c1ddb-104">Methods</span></span>  
  
|<span data-ttu-id="c1ddb-105">Methode</span><span class="sxs-lookup"><span data-stu-id="c1ddb-105">Method</span></span>|<span data-ttu-id="c1ddb-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1ddb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c1ddb-107">GetBindingIdentityFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="c1ddb-107">GetBindingIdentityFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|<span data-ttu-id="c1ddb-108">Ruft die assemblyidentitäts-Bindungs Daten für die Assembly am angegebenen Dateipfad ab.</span><span class="sxs-lookup"><span data-stu-id="c1ddb-108">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="c1ddb-109">GetBindingIdentityFromStream-Methode</span><span class="sxs-lookup"><span data-stu-id="c1ddb-109">GetBindingIdentityFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|<span data-ttu-id="c1ddb-110">Ruft die kanonischen Assemblyidentitätsdaten für die Assembly im angegebenen Stream ab.</span><span class="sxs-lookup"><span data-stu-id="c1ddb-110">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="c1ddb-111">GetCLRAssemblyReferenceList-Methode</span><span class="sxs-lookup"><span data-stu-id="c1ddb-111">GetCLRAssemblyReferenceList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|<span data-ttu-id="c1ddb-112">Ruft eine [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) -Instanz aus der angegebenen Liste der partiellen Assemblyidentitäten ab.</span><span class="sxs-lookup"><span data-stu-id="c1ddb-112">Gets an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>|  
|[<span data-ttu-id="c1ddb-113">GetProbingAssembliesFromReference-Methode</span><span class="sxs-lookup"><span data-stu-id="c1ddb-113">GetProbingAssembliesFromReference Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|<span data-ttu-id="c1ddb-114">Ruft einen [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) -Enumerator für die Assemblyidentitäten ab, auf die von der Assembly mit der angegebenen Identität verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="c1ddb-114">Gets an [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity.</span></span>|  
|[<span data-ttu-id="c1ddb-115">GetReferencedAssembliesFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="c1ddb-115">GetReferencedAssembliesFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|<span data-ttu-id="c1ddb-116">Ruft eine [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) -Instanz ab, die eine Liste der Assemblys enthält, auf die die Assembly am angegebenen Dateipfad verweist.</span><span class="sxs-lookup"><span data-stu-id="c1ddb-116">Gets an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="c1ddb-117">GetReferencedAssembliesFromStream-Methode</span><span class="sxs-lookup"><span data-stu-id="c1ddb-117">GetReferencedAssembliesFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|<span data-ttu-id="c1ddb-118">Ruft einen Zeiger auf ein `ICLRReferenceAssemblyEnum` Objekt ab, das Assemblyidentitätsdaten für die Assemblys enthält, auf die die Assembly im angegebenen Stream verweist.</span><span class="sxs-lookup"><span data-stu-id="c1ddb-118">Gets a pointer to an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="c1ddb-119">IsStronglyNamed-Methode</span><span class="sxs-lookup"><span data-stu-id="c1ddb-119">IsStronglyNamed Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-isstronglynamed-method.md)|<span data-ttu-id="c1ddb-120">Ruft einen Wert ab, der angibt, ob die angegebene Assembly einen starken Namen hat.</span><span class="sxs-lookup"><span data-stu-id="c1ddb-120">Gets a value that indicates whether the specified assembly is strongly named.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1ddb-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c1ddb-121">Remarks</span></span>  
 <span data-ttu-id="c1ddb-122">Verwenden Sie `ICLRAssemblyIdentityManager`, um Instanzen von `ICLRAssemblyReferenceList` und Assemblyidentitäten aufzuzählen.</span><span class="sxs-lookup"><span data-stu-id="c1ddb-122">Use `ICLRAssemblyIdentityManager` to get instances of `ICLRAssemblyReferenceList` and to enumerate assembly identities.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1ddb-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c1ddb-123">Requirements</span></span>  
 <span data-ttu-id="c1ddb-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1ddb-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1ddb-125">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="c1ddb-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c1ddb-126">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c1ddb-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c1ddb-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1ddb-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1ddb-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1ddb-128">See also</span></span>

- [<span data-ttu-id="c1ddb-129">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1ddb-129">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="c1ddb-130">ICLRProbingAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1ddb-130">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="c1ddb-131">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c1ddb-131">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
