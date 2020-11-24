---
title: ICLRAssemblyReferenceList-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList
helpviewer_keywords:
- ICLRAssemblyReferenceList interface [.NET Framework hosting]
ms.assetid: 5f890fdf-d22a-429e-a35f-135273d1a636
topic_type:
- apiref
ms.openlocfilehash: a75235cd0ac0e55412f0ba58881796e3ebc801f1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679217"
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="19ad8-102">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="19ad8-102">ICLRAssemblyReferenceList Interface</span></span>

<span data-ttu-id="19ad8-103">Verwaltet eine Liste von Assemblys, die vom Common Language Runtime (CLR) und nicht vom Host geladen werden.</span><span class="sxs-lookup"><span data-stu-id="19ad8-103">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="19ad8-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="19ad8-104">Methods</span></span>  
  
|<span data-ttu-id="19ad8-105">Methode</span><span class="sxs-lookup"><span data-stu-id="19ad8-105">Method</span></span>|<span data-ttu-id="19ad8-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="19ad8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="19ad8-107">IsAssemblyReferenceInList-Methode</span><span class="sxs-lookup"><span data-stu-id="19ad8-107">IsAssemblyReferenceInList Method</span></span>](iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="19ad8-108">Ruft einen Wert ab, der angibt, ob der angegebene Zeiger auf eine Assembly in der Liste verweist.</span><span class="sxs-lookup"><span data-stu-id="19ad8-108">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="19ad8-109">IsStringAssemblyReferenceInList-Methode</span><span class="sxs-lookup"><span data-stu-id="19ad8-109">IsStringAssemblyReferenceInList Method</span></span>](iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="19ad8-110">Ruft einen Wert ab, der angibt, ob der angegebene Name mit dem Namen einer Assembly in der Liste übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="19ad8-110">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19ad8-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="19ad8-111">Remarks</span></span>  

 <span data-ttu-id="19ad8-112">Aufrufen der [ICLRAssemblyIdentityManager:: GetCLRAssemblyReferenceList](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) -Methode, um einen Zeiger auf eine Instanz von zu erhalten `ICLRAssemblyReferenceList` .</span><span class="sxs-lookup"><span data-stu-id="19ad8-112">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19ad8-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="19ad8-113">Requirements</span></span>  

 <span data-ttu-id="19ad8-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19ad8-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19ad8-115">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="19ad8-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="19ad8-116">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="19ad8-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="19ad8-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19ad8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19ad8-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="19ad8-118">See also</span></span>

- [<span data-ttu-id="19ad8-119">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="19ad8-119">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="19ad8-120">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="19ad8-120">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="19ad8-121">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="19ad8-121">Hosting Interfaces</span></span>](hosting-interfaces.md)
