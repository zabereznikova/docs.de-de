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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4067c1fbcf99c903c892eaec58262d95569114b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61930038"
---
# <a name="ihostassemblystore-interface"></a><span data-ttu-id="cf0df-102">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cf0df-102">IHostAssemblyStore Interface</span></span>
<span data-ttu-id="cf0df-103">Enthält Methoden, die einen Host zum Laden von Assemblys und Modulen unabhängig von der die common Language Runtime (CLR) zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="cf0df-103">Provides methods that allow a host to load assemblies and modules independently of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cf0df-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="cf0df-104">Methods</span></span>  
  
|<span data-ttu-id="cf0df-105">Methode</span><span class="sxs-lookup"><span data-stu-id="cf0df-105">Method</span></span>|<span data-ttu-id="cf0df-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf0df-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cf0df-107">ProvideAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="cf0df-107">ProvideAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|<span data-ttu-id="cf0df-108">Ruft einen Verweis auf eine Assembly, die nicht verwiesen wird die [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) zurückgegeben, die von einem Aufruf von [IHostAssemblyManager:: GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span><span class="sxs-lookup"><span data-stu-id="cf0df-108">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) returned from a call to [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span>|  
|[<span data-ttu-id="cf0df-109">ProvideModule-Methode</span><span class="sxs-lookup"><span data-stu-id="cf0df-109">ProvideModule Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|<span data-ttu-id="cf0df-110">Löst ein Modul innerhalb einer Assembly oder eine verknüpfte (nicht eingebettete) Ressourcendatei an.</span><span class="sxs-lookup"><span data-stu-id="cf0df-110">Resolves a module within an assembly or a linked (not embedded) resource file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf0df-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cf0df-111">Remarks</span></span>  
 <span data-ttu-id="cf0df-112">`IHostAssemblyStore` bietet eine Möglichkeit für einen Host, Assemblys, die effizient basierend auf Assemblyidentität zu laden.</span><span class="sxs-lookup"><span data-stu-id="cf0df-112">`IHostAssemblyStore` provides a way for a host to load assemblies efficiently based on assembly identity.</span></span> <span data-ttu-id="cf0df-113">Der Host lädt Assemblys durch Rückgabe `IStream` Instanzen, die direkt auf die Bytes zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="cf0df-113">The host loads assemblies by returning `IStream` instances that point directly at the bytes.</span></span>  
  
 <span data-ttu-id="cf0df-114">Die CLR bestimmt, ob ein Host implementiert hat `IHostAssemblyStore` durch Aufrufen von `IHostAssemblyManager::GetNonHostAssemblyStores` bei der Initialisierung.</span><span class="sxs-lookup"><span data-stu-id="cf0df-114">The CLR determines whether a host has implemented `IHostAssemblyStore` by calling `IHostAssemblyManager::GetNonHostAssemblyStores` upon initialization.</span></span> <span data-ttu-id="cf0df-115">Dies ermöglicht dem Host, z. B. zum Binden an die Benutzer-Assemblys zu steuern, aber von der Common Language Runtime zum Binden an .NET Framework-Assemblys abhängig zu sein.</span><span class="sxs-lookup"><span data-stu-id="cf0df-115">This allows the host, for example, to control binding to user assemblies, but to rely on the runtime to bind to .NET Framework assemblies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf0df-116">Bereitstellen einer Implementierung von `IHostAssemblyStore`, gibt die Absicht, um alle Assemblys aufzulösen, die nicht verwiesen werden: der Host die `ICLRAssemblyReferenceList` Merry `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span><span class="sxs-lookup"><span data-stu-id="cf0df-116">In providing an implementation of `IHostAssemblyStore`, the host specifies its intent to resolve all assemblies that are not referenced by the `ICLRAssemblyReferenceList` returned from `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf0df-117">.NET Framework, Version 2.0 bietet keine Möglichkeit für den Host, der das systemeigene Abbild von einer Assembly lädt, gemäß Bereitstellung durch die [Native Image Generator (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) Hilfsprogramm.</span><span class="sxs-lookup"><span data-stu-id="cf0df-117">The .NET Framework version 2.0 does not provide a way for the host to load the native image of an assembly, as provided by the [Native Image Generator (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) utility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf0df-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cf0df-118">Requirements</span></span>  
 <span data-ttu-id="cf0df-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf0df-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf0df-120">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cf0df-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cf0df-121">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="cf0df-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cf0df-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf0df-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf0df-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf0df-123">See also</span></span>

- [<span data-ttu-id="cf0df-124">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cf0df-124">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="cf0df-125">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cf0df-125">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="cf0df-126">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="cf0df-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
