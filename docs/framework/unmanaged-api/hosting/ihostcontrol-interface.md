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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967730"
---
# <a name="ihostcontrol-interface"></a><span data-ttu-id="e71e5-102">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e71e5-102">IHostControl Interface</span></span>
<span data-ttu-id="e71e5-103">Stellt Methoden für das Laden von Assemblys zu konfigurieren und um zu bestimmen, welche hosting vom Host unterstützten Schnittstellen bereit.</span><span class="sxs-lookup"><span data-stu-id="e71e5-103">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e71e5-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e71e5-104">Methods</span></span>  
  
|<span data-ttu-id="e71e5-105">Methode</span><span class="sxs-lookup"><span data-stu-id="e71e5-105">Method</span></span>|<span data-ttu-id="e71e5-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e71e5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e71e5-107">GetHostManager-Methode</span><span class="sxs-lookup"><span data-stu-id="e71e5-107">GetHostManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)|<span data-ttu-id="e71e5-108">Ruft einen Schnittstellenzeiger auf den Host für die Implementierung der Schnittstelle ab, mit dem angegebenen `IID`.</span><span class="sxs-lookup"><span data-stu-id="e71e5-108">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>|  
|[<span data-ttu-id="e71e5-109">SetAppDomainManager-Methode</span><span class="sxs-lookup"><span data-stu-id="e71e5-109">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)|<span data-ttu-id="e71e5-110">Benachrichtigt den Host an, dass eine Anwendungsdomäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e71e5-110">Notifies the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e71e5-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e71e5-111">Requirements</span></span>  
 <span data-ttu-id="e71e5-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e71e5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e71e5-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e71e5-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e71e5-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e71e5-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e71e5-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e71e5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e71e5-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e71e5-116">See also</span></span>

- <xref:System.AppDomainManager>
- [<span data-ttu-id="e71e5-117">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e71e5-117">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="e71e5-118">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e71e5-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="e71e5-119">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e71e5-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
