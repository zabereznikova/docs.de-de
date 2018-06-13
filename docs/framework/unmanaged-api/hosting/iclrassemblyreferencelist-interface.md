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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 388b26a5559435ea57300751987d14bc5cb9d50c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435296"
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="6ac91-102">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6ac91-102">ICLRAssemblyReferenceList Interface</span></span>
<span data-ttu-id="6ac91-103">Verwaltet eine Liste der Assemblys, die von der common Language Runtime (CLR) und nicht vom Host geladen werden.</span><span class="sxs-lookup"><span data-stu-id="6ac91-103">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6ac91-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="6ac91-104">Methods</span></span>  
  
|<span data-ttu-id="6ac91-105">Methode</span><span class="sxs-lookup"><span data-stu-id="6ac91-105">Method</span></span>|<span data-ttu-id="6ac91-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6ac91-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6ac91-107">IsAssemblyReferenceInList-Methode</span><span class="sxs-lookup"><span data-stu-id="6ac91-107">IsAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="6ac91-108">Ruft einen Wert, der angibt, ob der angegebene Zeiger auf eine Assembly in der Liste verweist.</span><span class="sxs-lookup"><span data-stu-id="6ac91-108">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="6ac91-109">IsStringAssemblyReferenceInList-Methode</span><span class="sxs-lookup"><span data-stu-id="6ac91-109">IsStringAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="6ac91-110">Ruft einen Wert, der angibt, ob der angegebene Name den Namen einer Assembly in der Liste übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="6ac91-110">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ac91-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6ac91-111">Remarks</span></span>  
 <span data-ttu-id="6ac91-112">Rufen Sie die [ICLRAssemblyIdentityManager:: GetCLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) Methode, um einen Zeiger zu einer Instanz von `ICLRAssemblyReferenceList`.</span><span class="sxs-lookup"><span data-stu-id="6ac91-112">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ac91-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6ac91-113">Requirements</span></span>  
 <span data-ttu-id="6ac91-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ac91-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ac91-115">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6ac91-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6ac91-116">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6ac91-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6ac91-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ac91-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ac91-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ac91-118">See Also</span></span>  
 [<span data-ttu-id="6ac91-119">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6ac91-119">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="6ac91-120">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6ac91-120">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 [<span data-ttu-id="6ac91-121">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6ac91-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
