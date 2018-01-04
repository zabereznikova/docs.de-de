---
title: IHostAssemblyManager-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAssemblyManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAssemblyManager
helpviewer_keywords: IHostAssemblyManager interface [.NET Framework hosting]
ms.assetid: dfec05bb-3cd7-4bd5-b396-a4f097c3a636
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 351824c1b915183a8e157f5bb2e01a414027a178
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="1e131-102">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1e131-102">IHostAssemblyManager Interface</span></span>
<span data-ttu-id="1e131-103">Enthält Methoden, mit denen einen Host Sätze von Assemblys angeben, die von der common Language Runtime (CLR) oder vom Host geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="1e131-103">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1e131-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="1e131-104">Methods</span></span>  
  
|<span data-ttu-id="1e131-105">Methode</span><span class="sxs-lookup"><span data-stu-id="1e131-105">Method</span></span>|<span data-ttu-id="1e131-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1e131-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1e131-107">GetAssemblyStore-Methode</span><span class="sxs-lookup"><span data-stu-id="1e131-107">GetAssemblyStore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="1e131-108">Ruft einen Schnittstellenzeiger auf eine [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) , die die Liste der Assemblys, die vom Host geladen darstellt.</span><span class="sxs-lookup"><span data-stu-id="1e131-108">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="1e131-109">GetNonHostStoreAssemblies-Methode</span><span class="sxs-lookup"><span data-stu-id="1e131-109">GetNonHostStoreAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="1e131-110">Ruft einen Schnittstellenzeiger auf eine [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) , die die Liste der Assemblys, die der Host die CLR geladen erwartet darstellt.</span><span class="sxs-lookup"><span data-stu-id="1e131-110">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e131-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1e131-111">Remarks</span></span>  
 <span data-ttu-id="1e131-112">Der Host ist nicht erforderlich, um implementieren `IHostAssemblyManager` oder `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="1e131-112">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="1e131-113">Wenn der Host implementiert `IHostAssemblyManager`, müssen Sie auch implementieren `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="1e131-113">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="1e131-114">Die Laufzeit fragt eine `IHostAssemblyManager` durch Aufrufen [IHostControl:: GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) bei der Initialisierung mit einer `IID` von IID_IHostAssemblyManager aufruft.</span><span class="sxs-lookup"><span data-stu-id="1e131-114">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e131-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1e131-115">Requirements</span></span>  
 <span data-ttu-id="1e131-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e131-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e131-117">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1e131-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1e131-118">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1e131-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1e131-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e131-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e131-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e131-120">See Also</span></span>  
 [<span data-ttu-id="1e131-121">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1e131-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="1e131-122">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1e131-122">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 [<span data-ttu-id="1e131-123">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1e131-123">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 [<span data-ttu-id="1e131-124">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1e131-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
