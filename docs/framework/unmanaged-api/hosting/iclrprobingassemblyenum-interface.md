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
ms.openlocfilehash: 6df08889af30542af5a128cbffc38a57ce640fde
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728926"
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="14335-102">ICLRProbingAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="14335-102">ICLRProbingAssemblyEnum Interface</span></span>

<span data-ttu-id="14335-103">Stellt Methoden bereit, die es dem Host ermöglichen, die Such Identitäten einer Assembly mithilfe der internen Identitätsinformationen der Assembly zu erhalten, die für die Common Language Runtime (CLR) intern sind, ohne diese Identität erstellen oder verstehen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="14335-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="14335-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="14335-104">Methods</span></span>  
  
|<span data-ttu-id="14335-105">Methode</span><span class="sxs-lookup"><span data-stu-id="14335-105">Method</span></span>|<span data-ttu-id="14335-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="14335-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="14335-107">Get-Methode</span><span class="sxs-lookup"><span data-stu-id="14335-107">Get Method</span></span>](iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="14335-108">Ruft die Assemblyidentität am angegebenen Index ab.</span><span class="sxs-lookup"><span data-stu-id="14335-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14335-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="14335-109">Remarks</span></span>  

 <span data-ttu-id="14335-110">Methoden wie [ICLRAssemblyIdentityManager:: GetProbingAssembliesFromReference](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) geben eine `ICLRProbingAssemblyEnum` Instanz zurück.</span><span class="sxs-lookup"><span data-stu-id="14335-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14335-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="14335-111">Requirements</span></span>  

 <span data-ttu-id="14335-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14335-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14335-113">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="14335-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="14335-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="14335-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="14335-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14335-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14335-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="14335-116">See also</span></span>

- [<span data-ttu-id="14335-117">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="14335-117">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="14335-118">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="14335-118">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="14335-119">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="14335-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
