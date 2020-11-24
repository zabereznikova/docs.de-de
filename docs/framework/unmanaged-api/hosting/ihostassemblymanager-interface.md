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
ms.openlocfilehash: a06e7f13b6de9450aa2a81f28f591c0a3ce8db0f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680986"
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="7c177-102">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c177-102">IHostAssemblyManager Interface</span></span>

<span data-ttu-id="7c177-103">Stellt Methoden bereit, mit denen ein Host Assemblys angeben kann, die vom Common Language Runtime (CLR) oder vom Host geladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7c177-103">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7c177-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="7c177-104">Methods</span></span>  
  
|<span data-ttu-id="7c177-105">Methode</span><span class="sxs-lookup"><span data-stu-id="7c177-105">Method</span></span>|<span data-ttu-id="7c177-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7c177-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7c177-107">GetAssemblyStore-Methode</span><span class="sxs-lookup"><span data-stu-id="7c177-107">GetAssemblyStore Method</span></span>](ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="7c177-108">Ruft einen Schnittstellen Zeiger auf einen [IHostAssemblyStore](ihostassemblystore-interface.md) ab, der die Liste der vom Host geladenen Assemblys darstellt.</span><span class="sxs-lookup"><span data-stu-id="7c177-108">Gets an interface pointer to an [IHostAssemblyStore](ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="7c177-109">GetNonHostStoreAssemblies-Methode</span><span class="sxs-lookup"><span data-stu-id="7c177-109">GetNonHostStoreAssemblies Method</span></span>](ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="7c177-110">Ruft einen Schnittstellen Zeiger auf eine [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) ab, die die Liste der Assemblys darstellt, die der Host zum Laden der CLR erwartet.</span><span class="sxs-lookup"><span data-stu-id="7c177-110">Gets an interface pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c177-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7c177-111">Remarks</span></span>  

 <span data-ttu-id="7c177-112">Der Host muss oder nicht implementieren `IHostAssemblyManager` `IHostAssemblyStore` .</span><span class="sxs-lookup"><span data-stu-id="7c177-112">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="7c177-113">Wenn der Host implementiert `IHostAssemblyManager` , muss auch implementiert werden `IHostAssemblyStore` .</span><span class="sxs-lookup"><span data-stu-id="7c177-113">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="7c177-114">Die Lauf Zeit Abfrage für einen `IHostAssemblyManager` durch Aufrufen von [IHostControl:: GetHostManager](ihostcontrol-gethostmanager-method.md) bei der Initialisierung mit einem `IID` IID_IHostAssemblyManager.</span><span class="sxs-lookup"><span data-stu-id="7c177-114">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c177-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7c177-115">Requirements</span></span>  

 <span data-ttu-id="7c177-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c177-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c177-117">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="7c177-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c177-118">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7c177-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c177-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c177-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c177-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7c177-120">See also</span></span>

- [<span data-ttu-id="7c177-121">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c177-121">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="7c177-122">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c177-122">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="7c177-123">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c177-123">IHostControl Interface</span></span>](ihostcontrol-interface.md)
- [<span data-ttu-id="7c177-124">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7c177-124">Hosting Interfaces</span></span>](hosting-interfaces.md)
