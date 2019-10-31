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
ms.openlocfilehash: 444a78705c61d5a53764f55185ef1a907830bd71
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195885"
---
# <a name="ihostcontrol-interface"></a><span data-ttu-id="d015c-102">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d015c-102">IHostControl Interface</span></span>
<span data-ttu-id="d015c-103">Bietet Methoden zum Konfigurieren des Ladens von Assemblys und zum bestimmen, welche Hostingschnittstellen der Host unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d015c-103">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d015c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d015c-104">Methods</span></span>  
  
|<span data-ttu-id="d015c-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d015c-105">Method</span></span>|<span data-ttu-id="d015c-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d015c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d015c-107">GetHostManager-Methode</span><span class="sxs-lookup"><span data-stu-id="d015c-107">GetHostManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)|<span data-ttu-id="d015c-108">Ruft einen Schnittstellen Zeiger auf die Implementierung der-Schnittstelle des Hosts mit dem angegebenen `IID`ab.</span><span class="sxs-lookup"><span data-stu-id="d015c-108">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>|  
|[<span data-ttu-id="d015c-109">SetAppDomainManager-Methode</span><span class="sxs-lookup"><span data-stu-id="d015c-109">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)|<span data-ttu-id="d015c-110">Benachrichtigt den Host, dass eine Anwendungsdomäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="d015c-110">Notifies the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d015c-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d015c-111">Requirements</span></span>  
 <span data-ttu-id="d015c-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d015c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d015c-113">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="d015c-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d015c-114">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d015c-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d015c-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d015c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d015c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d015c-116">See also</span></span>

- <xref:System.AppDomainManager>
- [<span data-ttu-id="d015c-117">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d015c-117">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="d015c-118">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d015c-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="d015c-119">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d015c-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
