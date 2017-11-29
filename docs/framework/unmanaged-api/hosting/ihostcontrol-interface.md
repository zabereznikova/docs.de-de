---
title: IHostControl-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostControl
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostControl
helpviewer_keywords: IHostControl interface [.NET Framework hosting]
ms.assetid: a4ae0d1f-ade9-4b0a-a122-93ed11a5e6b3
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7e72ad562a73faf5682204c2ae2583b71cb3c05e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostcontrol-interface"></a><span data-ttu-id="d1e94-102">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d1e94-102">IHostControl Interface</span></span>
<span data-ttu-id="d1e94-103">Stellt Methoden für das Laden von Assemblys zu konfigurieren und um zu bestimmen, welche hosting vom Host unterstützten Schnittstellen bereit.</span><span class="sxs-lookup"><span data-stu-id="d1e94-103">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d1e94-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d1e94-104">Methods</span></span>  
  
|<span data-ttu-id="d1e94-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d1e94-105">Method</span></span>|<span data-ttu-id="d1e94-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d1e94-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d1e94-107">GetHostManager-Methode</span><span class="sxs-lookup"><span data-stu-id="d1e94-107">GetHostManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)|<span data-ttu-id="d1e94-108">Ruft einen Schnittstellenzeiger auf dem Host-Implementierung der Schnittstelle mit dem angegebenen `IID`.</span><span class="sxs-lookup"><span data-stu-id="d1e94-108">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>|  
|[<span data-ttu-id="d1e94-109">SetAppDomainManager-Methode</span><span class="sxs-lookup"><span data-stu-id="d1e94-109">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)|<span data-ttu-id="d1e94-110">Benachrichtigt den Host an, dass eine Anwendungsdomäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="d1e94-110">Notifies the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d1e94-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d1e94-111">Requirements</span></span>  
 <span data-ttu-id="d1e94-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1e94-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1e94-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d1e94-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d1e94-114">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d1e94-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d1e94-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1e94-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1e94-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1e94-116">See Also</span></span>  
 <xref:System.AppDomainManager>  
 [<span data-ttu-id="d1e94-117">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d1e94-117">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [<span data-ttu-id="d1e94-118">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d1e94-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="d1e94-119">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d1e94-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
