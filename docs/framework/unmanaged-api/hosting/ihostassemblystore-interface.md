---
title: IHostAssemblyStore-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore
helpviewer_keywords:
- IHostAssemblyStore interface [.NET Framework hosting]
ms.assetid: cccb650f-abe0-41e2-9fd1-b383788eb1f6
topic_type:
- apiref
ms.openlocfilehash: d7475e2423d4dc6f57e8928514d7991169eef232
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124499"
---
# <a name="ihostassemblystore-interface"></a><span data-ttu-id="7c966-102">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c966-102">IHostAssemblyStore Interface</span></span>
<span data-ttu-id="7c966-103">Stellt Methoden bereit, die einem Host das Laden von Assemblys und Modulen unabhängig von der Common Language Runtime (CLR) ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="7c966-103">Provides methods that allow a host to load assemblies and modules independently of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7c966-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="7c966-104">Methods</span></span>  
  
|<span data-ttu-id="7c966-105">Methode</span><span class="sxs-lookup"><span data-stu-id="7c966-105">Method</span></span>|<span data-ttu-id="7c966-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7c966-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7c966-107">ProvideAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="7c966-107">ProvideAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|<span data-ttu-id="7c966-108">Ruft einen Verweis auf eine Assembly ab, auf die von der [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) , die von einem [IHostAssemblyManager:: getnonhoststoreassemblys](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)zurückgegeben wurde, nicht verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="7c966-108">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) returned from a call to [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span>|  
|[<span data-ttu-id="7c966-109">ProvideModule-Methode</span><span class="sxs-lookup"><span data-stu-id="7c966-109">ProvideModule Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|<span data-ttu-id="7c966-110">Löst ein Modul in einer Assembly oder einer verknüpften (nicht eingebetteten) Ressourcen Datei auf.</span><span class="sxs-lookup"><span data-stu-id="7c966-110">Resolves a module within an assembly or a linked (not embedded) resource file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c966-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7c966-111">Remarks</span></span>  
 <span data-ttu-id="7c966-112">`IHostAssemblyStore` bietet eine Möglichkeit für einen Host, Assemblys basierend auf der Assemblyidentität effizient zu laden.</span><span class="sxs-lookup"><span data-stu-id="7c966-112">`IHostAssemblyStore` provides a way for a host to load assemblies efficiently based on assembly identity.</span></span> <span data-ttu-id="7c966-113">Der Host lädt Assemblys, indem `IStream` Instanzen zurückgegeben werden, die direkt auf die Bytes zeigen.</span><span class="sxs-lookup"><span data-stu-id="7c966-113">The host loads assemblies by returning `IStream` instances that point directly at the bytes.</span></span>  
  
 <span data-ttu-id="7c966-114">Die CLR bestimmt, ob ein Host `IHostAssemblyStore` implementiert hat, indem `IHostAssemblyManager::GetNonHostAssemblyStores` bei der Initialisierung aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="7c966-114">The CLR determines whether a host has implemented `IHostAssemblyStore` by calling `IHostAssemblyManager::GetNonHostAssemblyStores` upon initialization.</span></span> <span data-ttu-id="7c966-115">Dadurch kann der Host z. b. die Bindung an Benutzerassemblys steuern, sich jedoch auf die Laufzeit zum Binden an .NET Framework Assemblys verlassen.</span><span class="sxs-lookup"><span data-stu-id="7c966-115">This allows the host, for example, to control binding to user assemblies, but to rely on the runtime to bind to .NET Framework assemblies.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7c966-116">Wenn eine Implementierung von `IHostAssemblyStore`bereitgestellt wird, gibt der Host die Absicht an, alle Assemblys aufzulösen, auf die nicht durch die von `IHostAssemblyManager::GetNonHostStoreAssemblies`zurückgegebenen `ICLRAssemblyReferenceList` verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="7c966-116">In providing an implementation of `IHostAssemblyStore`, the host specifies its intent to resolve all assemblies that are not referenced by the `ICLRAssemblyReferenceList` returned from `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7c966-117">Der .NET Framework Version 2,0 bietet dem Host keine Möglichkeit, das systemeigene Image einer Assembly zu laden, wie vom systemeigenen [Image Generator (Ngen. exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="7c966-117">The .NET Framework version 2.0 does not provide a way for the host to load the native image of an assembly, as provided by the [Native Image Generator (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) utility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c966-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7c966-118">Requirements</span></span>  
 <span data-ttu-id="7c966-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c966-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c966-120">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="7c966-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c966-121">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7c966-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c966-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c966-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c966-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c966-123">See also</span></span>

- [<span data-ttu-id="7c966-124">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c966-124">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="7c966-125">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c966-125">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="7c966-126">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7c966-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
