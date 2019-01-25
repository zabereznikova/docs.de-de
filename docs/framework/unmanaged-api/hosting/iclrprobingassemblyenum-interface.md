---
title: ICLRProbingAssemblyEnum-Schnittstelle
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d471d7a33a048315b3a7fd9107baa0ad95a865c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54678771"
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="b8162-102">ICLRProbingAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8162-102">ICLRProbingAssemblyEnum Interface</span></span>
<span data-ttu-id="b8162-103">Bietet Methoden, mit denen der Host zum Abrufen der gesuchten Identitäten einer Assembly mit Informationen zur Identität der Assembly, die intern für die common Language Runtime (CLR), ohne Sie zu erstellen oder zu verstehen, die diese Identität.</span><span class="sxs-lookup"><span data-stu-id="b8162-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b8162-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="b8162-104">Methods</span></span>  
  
|<span data-ttu-id="b8162-105">Methode</span><span class="sxs-lookup"><span data-stu-id="b8162-105">Method</span></span>|<span data-ttu-id="b8162-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b8162-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b8162-107">Get-Methode</span><span class="sxs-lookup"><span data-stu-id="b8162-107">Get Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="b8162-108">Ruft die Identität der Assembly am angegebenen Index ab.</span><span class="sxs-lookup"><span data-stu-id="b8162-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8162-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b8162-109">Remarks</span></span>  
 <span data-ttu-id="b8162-110">Methoden, z. B. [ICLRAssemblyIdentityManager:: GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) Zurückgeben einer `ICLRProbingAssemblyEnum` Instanz.</span><span class="sxs-lookup"><span data-stu-id="b8162-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8162-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b8162-111">Requirements</span></span>  
 <span data-ttu-id="b8162-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8162-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8162-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b8162-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b8162-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b8162-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b8162-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8162-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8162-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8162-116">See also</span></span>
- [<span data-ttu-id="b8162-117">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8162-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="b8162-118">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8162-118">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="b8162-119">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b8162-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
