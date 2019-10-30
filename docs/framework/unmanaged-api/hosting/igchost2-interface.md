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
ms.openlocfilehash: 43c16415c91521194e0d88be84dd176c3fdadad1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134833"
---
# <a name="igchost2-interface"></a><span data-ttu-id="e6ee5-102">IGCHost2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e6ee5-102">IGCHost2 Interface</span></span>
<span data-ttu-id="e6ee5-103">Bietet Methoden zum Abrufen von Informationen über das Garbage Collection System und zum Steuern einiger Aspekte von Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="e6ee5-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e6ee5-104">Für eine neue Entwicklung empfiehlt es sich, stattdessen die [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) -Schnittstelle zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e6ee5-104">For new development, we recommend that you use the [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e6ee5-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="e6ee5-105">Methods</span></span>  
  
|<span data-ttu-id="e6ee5-106">Methode</span><span class="sxs-lookup"><span data-stu-id="e6ee5-106">Method</span></span>|<span data-ttu-id="e6ee5-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6ee5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e6ee5-108">SetGCStartupLimitsEx-Methode</span><span class="sxs-lookup"><span data-stu-id="e6ee5-108">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="e6ee5-109">Legt die Segmentgröße und die maximale Größe für die Generation 0 fest.</span><span class="sxs-lookup"><span data-stu-id="e6ee5-109">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="e6ee5-110">Aktiviert Generation 0 und Segment Größen, die größer als `DWORD`sind.</span><span class="sxs-lookup"><span data-stu-id="e6ee5-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e6ee5-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e6ee5-111">Requirements</span></span>  
 <span data-ttu-id="e6ee5-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6ee5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6ee5-113">**Header:** Gchost. idl, gchost. h</span><span class="sxs-lookup"><span data-stu-id="e6ee5-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="e6ee5-114">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e6ee5-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6ee5-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6ee5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6ee5-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6ee5-116">See also</span></span>

- [<span data-ttu-id="e6ee5-117">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e6ee5-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="e6ee5-118">CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e6ee5-118">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="e6ee5-119">CorRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="e6ee5-119">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
