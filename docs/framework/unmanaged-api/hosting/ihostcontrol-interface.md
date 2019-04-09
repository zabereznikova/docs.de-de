---
title: IHostControl-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl
helpviewer_keywords:
- IHostControl interface [.NET Framework hosting]
ms.assetid: a4ae0d1f-ade9-4b0a-a122-93ed11a5e6b3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 014e5c9951091046ae07374794743e82affcd5ad
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122264"
---
# <a name="ihostcontrol-interface"></a><span data-ttu-id="efaf7-102">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="efaf7-102">IHostControl Interface</span></span>
<span data-ttu-id="efaf7-103">Stellt Methoden für das Laden von Assemblys zu konfigurieren und um zu bestimmen, welche hosting vom Host unterstützten Schnittstellen bereit.</span><span class="sxs-lookup"><span data-stu-id="efaf7-103">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="efaf7-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="efaf7-104">Methods</span></span>  
  
|<span data-ttu-id="efaf7-105">Methode</span><span class="sxs-lookup"><span data-stu-id="efaf7-105">Method</span></span>|<span data-ttu-id="efaf7-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="efaf7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="efaf7-107">GetHostManager-Methode</span><span class="sxs-lookup"><span data-stu-id="efaf7-107">GetHostManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)|<span data-ttu-id="efaf7-108">Ruft einen Schnittstellenzeiger auf den Host für die Implementierung der Schnittstelle ab, mit dem angegebenen `IID`.</span><span class="sxs-lookup"><span data-stu-id="efaf7-108">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>|  
|[<span data-ttu-id="efaf7-109">SetAppDomainManager-Methode</span><span class="sxs-lookup"><span data-stu-id="efaf7-109">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)|<span data-ttu-id="efaf7-110">Benachrichtigt den Host an, dass eine Anwendungsdomäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="efaf7-110">Notifies the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="efaf7-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="efaf7-111">Requirements</span></span>  
 <span data-ttu-id="efaf7-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efaf7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efaf7-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="efaf7-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="efaf7-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="efaf7-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="efaf7-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="efaf7-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="efaf7-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="efaf7-116">See also</span></span>

- <xref:System.AppDomainManager>
- [<span data-ttu-id="efaf7-117">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="efaf7-117">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="efaf7-118">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="efaf7-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="efaf7-119">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="efaf7-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
