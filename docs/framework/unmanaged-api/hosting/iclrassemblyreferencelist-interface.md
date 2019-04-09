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
ms.openlocfilehash: 43c40e833e3a250239e9e90667196a2a74a96e0b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187654"
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="8ea7d-102">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8ea7d-102">ICLRAssemblyReferenceList Interface</span></span>
<span data-ttu-id="8ea7d-103">Verwaltet eine Liste der Assemblys, die durch die common Language Runtime (CLR) und nicht durch den Host geladen werden.</span><span class="sxs-lookup"><span data-stu-id="8ea7d-103">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8ea7d-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="8ea7d-104">Methods</span></span>  
  
|<span data-ttu-id="8ea7d-105">Methode</span><span class="sxs-lookup"><span data-stu-id="8ea7d-105">Method</span></span>|<span data-ttu-id="8ea7d-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8ea7d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8ea7d-107">IsAssemblyReferenceInList-Methode</span><span class="sxs-lookup"><span data-stu-id="8ea7d-107">IsAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="8ea7d-108">Ruft einen Wert, der angibt, ob der angegebene Zeiger auf eine Assembly in der Liste verweist.</span><span class="sxs-lookup"><span data-stu-id="8ea7d-108">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="8ea7d-109">IsStringAssemblyReferenceInList-Methode</span><span class="sxs-lookup"><span data-stu-id="8ea7d-109">IsStringAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="8ea7d-110">Ruft einen Wert, der angibt, ob der Name einer Assembly in der Liste mit dem angegebene Namen übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="8ea7d-110">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ea7d-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8ea7d-111">Remarks</span></span>  
 <span data-ttu-id="8ea7d-112">Rufen Sie die [ICLRAssemblyIdentityManager:: GetCLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) Methode zum Abrufen eines Zeigers auf eine Instanz von `ICLRAssemblyReferenceList`.</span><span class="sxs-lookup"><span data-stu-id="8ea7d-112">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ea7d-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8ea7d-113">Requirements</span></span>  
 <span data-ttu-id="8ea7d-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ea7d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ea7d-115">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8ea7d-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8ea7d-116">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8ea7d-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="8ea7d-117">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="8ea7d-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8ea7d-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ea7d-118">See also</span></span>

- [<span data-ttu-id="8ea7d-119">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8ea7d-119">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="8ea7d-120">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8ea7d-120">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="8ea7d-121">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="8ea7d-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
