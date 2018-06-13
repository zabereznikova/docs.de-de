---
title: IGCHost2-Schnittstelle
ms.date: 03/30/2017
api_name:
- IGCHost2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2
helpviewer_keywords:
- IGCHost2 interface [.NET Framework hosting]
ms.assetid: e5323fa4-18ac-424d-859d-a65a550d08d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c6cbf44bd02a45b9b99d2dad63fc5bd6219c4ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437676"
---
# <a name="igchost2-interface"></a><span data-ttu-id="1d9f8-102">IGCHost2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d9f8-102">IGCHost2 Interface</span></span>
<span data-ttu-id="1d9f8-103">Stellt Methoden zum Abrufen von Informationen über die Garbage Collection-System und zum Steuern des einige Aspekte der Garbagecollection.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1d9f8-104">Für Neuentwicklungen, wir empfehlen die Verwendung der [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-104">For new development, we recommend that you use the [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1d9f8-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="1d9f8-105">Methods</span></span>  
  
|<span data-ttu-id="1d9f8-106">Methode</span><span class="sxs-lookup"><span data-stu-id="1d9f8-106">Method</span></span>|<span data-ttu-id="1d9f8-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1d9f8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1d9f8-108">SetGCStartupLimitsEx-Methode</span><span class="sxs-lookup"><span data-stu-id="1d9f8-108">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="1d9f8-109">Legt die Größe des Segments und die maximale Größe für Generation 0 fest.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-109">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="1d9f8-110">Ermöglicht die Generation 0 und größer als Größe der Segmente `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1d9f8-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1d9f8-111">Requirements</span></span>  
 <span data-ttu-id="1d9f8-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d9f8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d9f8-113">**Header:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="1d9f8-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="1d9f8-114">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1d9f8-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d9f8-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d9f8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d9f8-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d9f8-116">See Also</span></span>  
 [<span data-ttu-id="1d9f8-117">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1d9f8-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="1d9f8-118">CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="1d9f8-118">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="1d9f8-119">CorRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="1d9f8-119">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
