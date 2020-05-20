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
ms.openlocfilehash: e1e114070f39e75254fc1bc0f8c1bf3e4733d5a2
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703369"
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="1606a-102">ICLRProbingAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1606a-102">ICLRProbingAssemblyEnum Interface</span></span>
<span data-ttu-id="1606a-103">Stellt Methoden bereit, die es dem Host ermöglichen, die Such Identitäten einer Assembly mithilfe der internen Identitätsinformationen der Assembly zu erhalten, die für die Common Language Runtime (CLR) intern sind, ohne diese Identität erstellen oder verstehen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="1606a-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1606a-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="1606a-104">Methods</span></span>  
  
|<span data-ttu-id="1606a-105">Methode</span><span class="sxs-lookup"><span data-stu-id="1606a-105">Method</span></span>|<span data-ttu-id="1606a-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1606a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1606a-107">Get-Methode</span><span class="sxs-lookup"><span data-stu-id="1606a-107">Get Method</span></span>](iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="1606a-108">Ruft die Assemblyidentität am angegebenen Index ab.</span><span class="sxs-lookup"><span data-stu-id="1606a-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1606a-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1606a-109">Remarks</span></span>  
 <span data-ttu-id="1606a-110">Methoden wie [ICLRAssemblyIdentityManager:: GetProbingAssembliesFromReference](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) geben eine `ICLRProbingAssemblyEnum` Instanz zurück.</span><span class="sxs-lookup"><span data-stu-id="1606a-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1606a-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1606a-111">Requirements</span></span>  
 <span data-ttu-id="1606a-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1606a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1606a-113">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="1606a-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1606a-114">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1606a-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1606a-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1606a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1606a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1606a-116">See also</span></span>

- [<span data-ttu-id="1606a-117">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1606a-117">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="1606a-118">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1606a-118">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="1606a-119">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="1606a-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
