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
ms.openlocfilehash: 1bffef31702aa051d9ca865b18a67ac90c00cd00
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680656"
---
# <a name="ihostcontrol-interface"></a><span data-ttu-id="93b3b-102">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="93b3b-102">IHostControl Interface</span></span>

<span data-ttu-id="93b3b-103">Bietet Methoden zum Konfigurieren des Ladens von Assemblys und zum bestimmen, welche Hostingschnittstellen der Host unterstützt.</span><span class="sxs-lookup"><span data-stu-id="93b3b-103">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="93b3b-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="93b3b-104">Methods</span></span>  
  
|<span data-ttu-id="93b3b-105">Methode</span><span class="sxs-lookup"><span data-stu-id="93b3b-105">Method</span></span>|<span data-ttu-id="93b3b-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="93b3b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="93b3b-107">GetHostManager-Methode</span><span class="sxs-lookup"><span data-stu-id="93b3b-107">GetHostManager Method</span></span>](ihostcontrol-gethostmanager-method.md)|<span data-ttu-id="93b3b-108">Ruft einen Schnittstellen Zeiger auf die Implementierung der-Schnittstelle des Hosts mit dem angegebenen ab `IID` .</span><span class="sxs-lookup"><span data-stu-id="93b3b-108">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>|  
|[<span data-ttu-id="93b3b-109">SetAppDomainManager-Methode</span><span class="sxs-lookup"><span data-stu-id="93b3b-109">SetAppDomainManager Method</span></span>](ihostcontrol-setappdomainmanager-method.md)|<span data-ttu-id="93b3b-110">Benachrichtigt den Host, dass eine Anwendungsdomäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="93b3b-110">Notifies the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="93b3b-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="93b3b-111">Requirements</span></span>  

 <span data-ttu-id="93b3b-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93b3b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93b3b-113">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="93b3b-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="93b3b-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="93b3b-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="93b3b-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93b3b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93b3b-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="93b3b-116">See also</span></span>

- <xref:System.AppDomainManager>
- [<span data-ttu-id="93b3b-117">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="93b3b-117">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
- [<span data-ttu-id="93b3b-118">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="93b3b-118">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="93b3b-119">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="93b3b-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
