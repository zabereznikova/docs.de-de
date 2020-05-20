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
ms.openlocfilehash: f1aa40ef868bf6ff7730e01ab66a6fec58af1196
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615877"
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="07e7c-102">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07e7c-102">ICLRAssemblyReferenceList Interface</span></span>
<span data-ttu-id="07e7c-103">Verwaltet eine Liste von Assemblys, die vom Common Language Runtime (CLR) und nicht vom Host geladen werden.</span><span class="sxs-lookup"><span data-stu-id="07e7c-103">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="07e7c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="07e7c-104">Methods</span></span>  
  
|<span data-ttu-id="07e7c-105">Methode</span><span class="sxs-lookup"><span data-stu-id="07e7c-105">Method</span></span>|<span data-ttu-id="07e7c-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="07e7c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="07e7c-107">IsAssemblyReferenceInList-Methode</span><span class="sxs-lookup"><span data-stu-id="07e7c-107">IsAssemblyReferenceInList Method</span></span>](iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="07e7c-108">Ruft einen Wert ab, der angibt, ob der angegebene Zeiger auf eine Assembly in der Liste verweist.</span><span class="sxs-lookup"><span data-stu-id="07e7c-108">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="07e7c-109">IsStringAssemblyReferenceInList-Methode</span><span class="sxs-lookup"><span data-stu-id="07e7c-109">IsStringAssemblyReferenceInList Method</span></span>](iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="07e7c-110">Ruft einen Wert ab, der angibt, ob der angegebene Name mit dem Namen einer Assembly in der Liste übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="07e7c-110">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07e7c-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="07e7c-111">Remarks</span></span>  
 <span data-ttu-id="07e7c-112">Aufrufen der [ICLRAssemblyIdentityManager:: GetCLRAssemblyReferenceList](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) -Methode, um einen Zeiger auf eine Instanz von zu erhalten `ICLRAssemblyReferenceList` .</span><span class="sxs-lookup"><span data-stu-id="07e7c-112">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07e7c-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="07e7c-113">Requirements</span></span>  
 <span data-ttu-id="07e7c-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07e7c-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07e7c-115">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="07e7c-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="07e7c-116">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="07e7c-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="07e7c-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07e7c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07e7c-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07e7c-118">See also</span></span>

- [<span data-ttu-id="07e7c-119">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07e7c-119">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="07e7c-120">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07e7c-120">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="07e7c-121">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="07e7c-121">Hosting Interfaces</span></span>](hosting-interfaces.md)
