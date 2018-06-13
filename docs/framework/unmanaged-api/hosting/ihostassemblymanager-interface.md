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
ms.openlocfilehash: c8c8d17723481fc5b41fe5f3006fe8db2c53d1ea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438479"
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="6e137-102">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e137-102">IHostAssemblyManager Interface</span></span>
<span data-ttu-id="6e137-103">Enthält Methoden, mit denen einen Host Sätze von Assemblys angeben, die von der common Language Runtime (CLR) oder vom Host geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="6e137-103">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6e137-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="6e137-104">Methods</span></span>  
  
|<span data-ttu-id="6e137-105">Methode</span><span class="sxs-lookup"><span data-stu-id="6e137-105">Method</span></span>|<span data-ttu-id="6e137-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6e137-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6e137-107">GetAssemblyStore-Methode</span><span class="sxs-lookup"><span data-stu-id="6e137-107">GetAssemblyStore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="6e137-108">Ruft einen Schnittstellenzeiger auf eine [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) , die die Liste der Assemblys, die vom Host geladen darstellt.</span><span class="sxs-lookup"><span data-stu-id="6e137-108">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="6e137-109">GetNonHostStoreAssemblies-Methode</span><span class="sxs-lookup"><span data-stu-id="6e137-109">GetNonHostStoreAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="6e137-110">Ruft einen Schnittstellenzeiger auf eine [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) , die die Liste der Assemblys, die der Host die CLR geladen erwartet darstellt.</span><span class="sxs-lookup"><span data-stu-id="6e137-110">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e137-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6e137-111">Remarks</span></span>  
 <span data-ttu-id="6e137-112">Der Host ist nicht erforderlich, um implementieren `IHostAssemblyManager` oder `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="6e137-112">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="6e137-113">Wenn der Host implementiert `IHostAssemblyManager`, müssen Sie auch implementieren `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="6e137-113">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="6e137-114">Die Laufzeit fragt eine `IHostAssemblyManager` durch Aufrufen [IHostControl:: GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) bei der Initialisierung mit einer `IID` von IID_IHostAssemblyManager aufruft.</span><span class="sxs-lookup"><span data-stu-id="6e137-114">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e137-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6e137-115">Requirements</span></span>  
 <span data-ttu-id="6e137-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e137-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e137-117">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6e137-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6e137-118">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6e137-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6e137-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e137-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e137-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e137-120">See Also</span></span>  
 [<span data-ttu-id="6e137-121">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e137-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="6e137-122">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e137-122">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 [<span data-ttu-id="6e137-123">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e137-123">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 [<span data-ttu-id="6e137-124">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6e137-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
