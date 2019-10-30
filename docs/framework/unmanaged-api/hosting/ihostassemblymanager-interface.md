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
ms.openlocfilehash: d9feeaf5f85d6f84a13e74a893b82c97fdaf023c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124510"
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="55e26-102">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="55e26-102">IHostAssemblyManager Interface</span></span>
<span data-ttu-id="55e26-103">Stellt Methoden bereit, mit denen ein Host Assemblys angeben kann, die vom Common Language Runtime (CLR) oder vom Host geladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="55e26-103">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="55e26-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="55e26-104">Methods</span></span>  
  
|<span data-ttu-id="55e26-105">Methode</span><span class="sxs-lookup"><span data-stu-id="55e26-105">Method</span></span>|<span data-ttu-id="55e26-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55e26-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="55e26-107">GetAssemblyStore-Methode</span><span class="sxs-lookup"><span data-stu-id="55e26-107">GetAssemblyStore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="55e26-108">Ruft einen Schnittstellen Zeiger auf einen [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) ab, der die Liste der vom Host geladenen Assemblys darstellt.</span><span class="sxs-lookup"><span data-stu-id="55e26-108">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="55e26-109">GetNonHostStoreAssemblies-Methode</span><span class="sxs-lookup"><span data-stu-id="55e26-109">GetNonHostStoreAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="55e26-110">Ruft einen Schnittstellen Zeiger auf eine [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) ab, die die Liste der Assemblys darstellt, die der Host zum Laden der CLR erwartet.</span><span class="sxs-lookup"><span data-stu-id="55e26-110">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55e26-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="55e26-111">Remarks</span></span>  
 <span data-ttu-id="55e26-112">Der Host muss `IHostAssemblyManager` oder `IHostAssemblyStore`nicht implementieren.</span><span class="sxs-lookup"><span data-stu-id="55e26-112">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="55e26-113">Wenn der Host `IHostAssemblyManager`implementiert, muss auch `IHostAssemblyStore`implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="55e26-113">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="55e26-114">Die Laufzeit fragt eine `IHostAssemblyManager` ab, indem Sie [IHostControl:: GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) bei der Initialisierung mit einer `IID` von IID_IHostAssemblyManager aufrufen.</span><span class="sxs-lookup"><span data-stu-id="55e26-114">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55e26-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="55e26-115">Requirements</span></span>  
 <span data-ttu-id="55e26-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55e26-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55e26-117">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="55e26-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="55e26-118">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="55e26-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55e26-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55e26-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55e26-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55e26-120">See also</span></span>

- [<span data-ttu-id="55e26-121">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="55e26-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="55e26-122">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="55e26-122">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="55e26-123">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="55e26-123">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="55e26-124">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="55e26-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
