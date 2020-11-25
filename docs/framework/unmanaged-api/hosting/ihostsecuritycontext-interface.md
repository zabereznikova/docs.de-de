---
title: IHostSecurityContext-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityContext
helpviewer_keywords:
- IHostSecurityContext interface [.NET Framework hosting]
ms.assetid: 88e2eac0-8ccb-404f-abbc-287d55159842
topic_type:
- apiref
ms.openlocfilehash: aafaa1d648396ddaa76193fa15cf7f74394777a9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724805"
---
# <a name="ihostsecuritycontext-interface"></a><span data-ttu-id="5559e-102">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5559e-102">IHostSecurityContext Interface</span></span>

<span data-ttu-id="5559e-103">Ermöglicht dem Common Language Runtime (CLR), Sicherheitskontext Informationen beizubehalten, die vom Host implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="5559e-103">Allows the common language runtime (CLR) to maintain security context information implemented by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5559e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="5559e-104">Methods</span></span>  
  
|<span data-ttu-id="5559e-105">Methode</span><span class="sxs-lookup"><span data-stu-id="5559e-105">Method</span></span>|<span data-ttu-id="5559e-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5559e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5559e-107">Capture-Methode</span><span class="sxs-lookup"><span data-stu-id="5559e-107">Capture Method</span></span>](ihostsecuritycontext-capture-method.md)|<span data-ttu-id="5559e-108">Ruft einen Klon der- `IHostSecurityContext` Instanz ab, die von einem [IHostSecurityManager:: GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md)-Befehl zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5559e-108">Gets a clone of the `IHostSecurityContext` instance returned from a call to [IHostSecurityManager::GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5559e-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5559e-109">Remarks</span></span>  

 <span data-ttu-id="5559e-110">Ein Host kann den gesamten Code Zugriff auf Thread Token sowohl durch den CLR-als auch durch den Benutzercode steuern.</span><span class="sxs-lookup"><span data-stu-id="5559e-110">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="5559e-111">Außerdem kann sichergestellt werden, dass die umfassenden Sicherheitskontext Informationen über asynchrone Vorgänge oder Code Punkte mit eingeschränktem Code Zugriff übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="5559e-111">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="5559e-112">`IHostSecurityContext` kapselt diese Sicherheitskontext Informationen, die für die Laufzeit nicht transparent sind.</span><span class="sxs-lookup"><span data-stu-id="5559e-112">`IHostSecurityContext` encapsulates this security context information, which is opaque to the runtime.</span></span> <span data-ttu-id="5559e-113">Die Laufzeit erfasst diese Informationen mithilfe von `Capture` und verschiebt Sie über die Verteilung des workerelements des Thread Pools, die Finalizer-Ausführung sowie Module-und Klassenkonstruktoren.</span><span class="sxs-lookup"><span data-stu-id="5559e-113">The runtime captures this information using `Capture`, and moves it across thread pool worker item dispatch, finalizer execution, and module and class constructors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5559e-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5559e-114">Requirements</span></span>  

 <span data-ttu-id="5559e-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5559e-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5559e-116">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="5559e-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5559e-117">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5559e-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5559e-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5559e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5559e-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5559e-119">See also</span></span>

- [<span data-ttu-id="5559e-120">ICLRHostProtectionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5559e-120">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="5559e-121">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5559e-121">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="5559e-122">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5559e-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
