---
title: IHostAssemblyManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager
helpviewer_keywords:
- IHostAssemblyManager interface [.NET Framework hosting]
ms.assetid: dfec05bb-3cd7-4bd5-b396-a4f097c3a636
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e300d4645939a131ceb8206999d95056b96a678
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59118949"
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="614ec-102">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="614ec-102">IHostAssemblyManager Interface</span></span>
<span data-ttu-id="614ec-103">Bietet Methoden, mit denen einen Host aus, um Assemblys anzugeben, die von der common Language Runtime (CLR) oder vom Host geladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="614ec-103">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="614ec-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="614ec-104">Methods</span></span>  
  
|<span data-ttu-id="614ec-105">Methode</span><span class="sxs-lookup"><span data-stu-id="614ec-105">Method</span></span>|<span data-ttu-id="614ec-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="614ec-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="614ec-107">GetAssemblyStore-Methode</span><span class="sxs-lookup"><span data-stu-id="614ec-107">GetAssemblyStore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="614ec-108">Ruft einen Schnittstellenzeiger auf ein [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) , das die Liste der Assemblys, die vom Host geladen darstellt.</span><span class="sxs-lookup"><span data-stu-id="614ec-108">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="614ec-109">GetNonHostStoreAssemblies-Methode</span><span class="sxs-lookup"><span data-stu-id="614ec-109">GetNonHostStoreAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="614ec-110">Ruft einen Schnittstellenzeiger auf ein [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) , das die Liste der Assemblys, die der Host die CLR geladen erwartet darstellt.</span><span class="sxs-lookup"><span data-stu-id="614ec-110">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="614ec-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="614ec-111">Remarks</span></span>  
 <span data-ttu-id="614ec-112">Der Host ist nicht erforderlich, um implementieren `IHostAssemblyManager` oder `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="614ec-112">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="614ec-113">Wenn der Host implementiert `IHostAssemblyManager`, muss er auch implementieren `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="614ec-113">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="614ec-114">Fragt die Runtime für eine `IHostAssemblyManager` durch Aufrufen von [IHostControl:: GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) bei der Initialisierung mit einer `IID` von IID_IHostAssemblyManager aufruft.</span><span class="sxs-lookup"><span data-stu-id="614ec-114">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="614ec-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="614ec-115">Requirements</span></span>  
 <span data-ttu-id="614ec-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="614ec-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="614ec-117">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="614ec-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="614ec-118">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="614ec-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="614ec-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="614ec-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="614ec-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="614ec-120">See also</span></span>

- [<span data-ttu-id="614ec-121">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="614ec-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="614ec-122">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="614ec-122">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="614ec-123">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="614ec-123">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="614ec-124">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="614ec-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
