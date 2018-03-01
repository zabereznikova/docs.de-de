---
title: ICLRProbingAssemblyEnum-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRProbingAssemblyEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum
helpviewer_keywords:
- ICLRProbingAssemblyEnum interface [.NET Framework hosting]
ms.assetid: e7d3ccab-b0f0-4872-8935-0ed72920171b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 31f3bfcb2b70bda952f0e4bb43dd8b0067e6ef1a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="7378d-102">ICLRProbingAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7378d-102">ICLRProbingAssemblyEnum Interface</span></span>
<span data-ttu-id="7378d-103">Enthält Methoden, mit denen der Host zum Abrufen der gesuchten Identitäten einer Assembly mit der Assembly aneinander gehängt Identitätsinformationen, die intern für die common Language Runtime (CLR), ohne zu erstellen oder zu verstehen, die Identität an.</span><span class="sxs-lookup"><span data-stu-id="7378d-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7378d-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="7378d-104">Methods</span></span>  
  
|<span data-ttu-id="7378d-105">Methode</span><span class="sxs-lookup"><span data-stu-id="7378d-105">Method</span></span>|<span data-ttu-id="7378d-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7378d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7378d-107">Get-Methode</span><span class="sxs-lookup"><span data-stu-id="7378d-107">Get Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="7378d-108">Ruft die Identität der Assembly am angegebenen Index ab.</span><span class="sxs-lookup"><span data-stu-id="7378d-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7378d-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7378d-109">Remarks</span></span>  
 <span data-ttu-id="7378d-110">Methoden, z. B. [ICLRAssemblyIdentityManager:: GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) Zurückgeben einer `ICLRProbingAssemblyEnum` Instanz.</span><span class="sxs-lookup"><span data-stu-id="7378d-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7378d-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7378d-111">Requirements</span></span>  
 <span data-ttu-id="7378d-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7378d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7378d-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7378d-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7378d-114">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7378d-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7378d-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7378d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7378d-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7378d-116">See Also</span></span>  
 [<span data-ttu-id="7378d-117">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7378d-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="7378d-118">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7378d-118">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="7378d-119">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7378d-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
