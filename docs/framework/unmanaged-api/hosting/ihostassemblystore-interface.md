---
title: IHostAssemblyStore-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAssemblyStore
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAssemblyStore
helpviewer_keywords: IHostAssemblyStore interface [.NET Framework hosting]
ms.assetid: cccb650f-abe0-41e2-9fd1-b383788eb1f6
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 284afbe73bea28a0aafe8d5e9e030c43be94aea4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostassemblystore-interface"></a><span data-ttu-id="6fafc-102">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6fafc-102">IHostAssemblyStore Interface</span></span>
<span data-ttu-id="6fafc-103">Enthält Methoden, die einen Host zum Laden von Assemblys und Modulen unabhängig von der common Language Runtime (CLR) zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="6fafc-103">Provides methods that allow a host to load assemblies and modules independently of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6fafc-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="6fafc-104">Methods</span></span>  
  
|<span data-ttu-id="6fafc-105">Methode</span><span class="sxs-lookup"><span data-stu-id="6fafc-105">Method</span></span>|<span data-ttu-id="6fafc-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6fafc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6fafc-107">ProvideAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="6fafc-107">ProvideAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|<span data-ttu-id="6fafc-108">Ruft einen Verweis auf eine Assembly, die nicht verwiesen wird die [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) von einem Aufruf zurückgegebene [IHostAssemblyManager:: GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span><span class="sxs-lookup"><span data-stu-id="6fafc-108">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) returned from a call to [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span>|  
|[<span data-ttu-id="6fafc-109">ProvideModule-Methode</span><span class="sxs-lookup"><span data-stu-id="6fafc-109">ProvideModule Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|<span data-ttu-id="6fafc-110">Löst ein Modul innerhalb einer Assembly oder einer verknüpften (nicht eingebetteten) Ressourcendatei.</span><span class="sxs-lookup"><span data-stu-id="6fafc-110">Resolves a module within an assembly or a linked (not embedded) resource file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6fafc-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6fafc-111">Remarks</span></span>  
 <span data-ttu-id="6fafc-112">`IHostAssemblyStore`bietet eine Möglichkeit für einen Host zum Laden von Assemblys, die effizient basierend auf Assemblyidentität.</span><span class="sxs-lookup"><span data-stu-id="6fafc-112">`IHostAssemblyStore` provides a way for a host to load assemblies efficiently based on assembly identity.</span></span> <span data-ttu-id="6fafc-113">Der Host lädt Assemblys durch Rückgabe `IStream` Instanzen, die direkt auf die Bytes verweisen.</span><span class="sxs-lookup"><span data-stu-id="6fafc-113">The host loads assemblies by returning `IStream` instances that point directly at the bytes.</span></span>  
  
 <span data-ttu-id="6fafc-114">Die CLR bestimmt, ob ein Host implementiert hat `IHostAssemblyStore` durch Aufrufen von `IHostAssemblyManager::GetNonHostAssemblyStores` bei der Initialisierung.</span><span class="sxs-lookup"><span data-stu-id="6fafc-114">The CLR determines whether a host has implemented `IHostAssemblyStore` by calling `IHostAssemblyManager::GetNonHostAssemblyStores` upon initialization.</span></span> <span data-ttu-id="6fafc-115">Dies ermöglicht dem Host, z. B. Benutzerassemblys Bindung steuern, sondern beruhen auf die Laufzeit in .NET Framework-Assemblys zu binden.</span><span class="sxs-lookup"><span data-stu-id="6fafc-115">This allows the host, for example, to control binding to user assemblies, but to rely on the runtime to bind to .NET Framework assemblies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6fafc-116">Bereitstellen einer Implementierung von `IHostAssemblyStore`, gibt die Absicht, beheben Sie alle Assemblys, die nicht verwiesen werden der Host die `ICLRAssemblyReferenceList` Merry `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span><span class="sxs-lookup"><span data-stu-id="6fafc-116">In providing an implementation of `IHostAssemblyStore`, the host specifies its intent to resolve all assemblies that are not referenced by the `ICLRAssemblyReferenceList` returned from `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6fafc-117">.NET Framework, Version 2.0 bietet keine Möglichkeit für den Host das systemeigene Image einer Assembly zu laden, gemäß der [Native Image Generator (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) Hilfsprogramm.</span><span class="sxs-lookup"><span data-stu-id="6fafc-117">The .NET Framework version 2.0 does not provide a way for the host to load the native image of an assembly, as provided by the [Native Image Generator (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) utility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fafc-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6fafc-118">Requirements</span></span>  
 <span data-ttu-id="6fafc-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fafc-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fafc-120">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6fafc-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6fafc-121">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6fafc-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6fafc-122">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fafc-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fafc-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6fafc-123">See Also</span></span>  
 [<span data-ttu-id="6fafc-124">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6fafc-124">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="6fafc-125">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6fafc-125">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="6fafc-126">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6fafc-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
