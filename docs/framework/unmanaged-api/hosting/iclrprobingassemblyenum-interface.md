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
ms.openlocfilehash: e1459c1604f3f8f043fd9b61533235ab7861c910
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120558"
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="50b80-102">ICLRProbingAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50b80-102">ICLRProbingAssemblyEnum Interface</span></span>
<span data-ttu-id="50b80-103">Stellt Methoden bereit, die es dem Host ermöglichen, die Such Identitäten einer Assembly mithilfe der internen Identitätsinformationen der Assembly zu erhalten, die für die Common Language Runtime (CLR) intern sind, ohne diese Identität erstellen oder verstehen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="50b80-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="50b80-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="50b80-104">Methods</span></span>  
  
|<span data-ttu-id="50b80-105">Methode</span><span class="sxs-lookup"><span data-stu-id="50b80-105">Method</span></span>|<span data-ttu-id="50b80-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="50b80-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="50b80-107">Get-Methode</span><span class="sxs-lookup"><span data-stu-id="50b80-107">Get Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="50b80-108">Ruft die Assemblyidentität am angegebenen Index ab.</span><span class="sxs-lookup"><span data-stu-id="50b80-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50b80-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="50b80-109">Remarks</span></span>  
 <span data-ttu-id="50b80-110">Methoden wie [ICLRAssemblyIdentityManager:: GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) geben eine `ICLRProbingAssemblyEnum` Instanz zurück.</span><span class="sxs-lookup"><span data-stu-id="50b80-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50b80-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="50b80-111">Requirements</span></span>  
 <span data-ttu-id="50b80-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50b80-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50b80-113">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="50b80-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="50b80-114">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="50b80-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="50b80-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50b80-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50b80-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50b80-116">See also</span></span>

- [<span data-ttu-id="50b80-117">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50b80-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="50b80-118">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50b80-118">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="50b80-119">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="50b80-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
