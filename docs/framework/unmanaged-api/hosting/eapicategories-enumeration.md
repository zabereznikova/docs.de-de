---
title: EApiCategories-Enumeration
ms.date: 03/30/2017
api_name:
- EApiCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EApiCategories
helpviewer_keywords:
- EApiCategories enumeration [.NET Framework hosting]
ms.assetid: 3c4a8a5a-8a46-4ac9-947f-4959bc9d6ac6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3debd3f13d78841188dd8c900f51c0110e1d4c67
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59086454"
---
# <a name="eapicategories-enumeration"></a><span data-ttu-id="a0fbd-102">EApiCategories-Enumeration</span><span class="sxs-lookup"><span data-stu-id="a0fbd-102">EApiCategories Enumeration</span></span>
<span data-ttu-id="a0fbd-103">Beschreibt die Kategorien von Funktionen, die der Host blockieren kann, Ausführen in teilweise vertrauenswürdigen Code.</span><span class="sxs-lookup"><span data-stu-id="a0fbd-103">Describes the categories of capabilities that the host can block from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0fbd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0fbd-104">Syntax</span></span>  
  
```  
typedef enum {  
    eNoCategory               = 0,  
    eSynchronization          = 0x1,  
    eSharedState              = 0x2,  
    eExternalProcessMgmt      = 0x4,  
    eSelfAffectingProcessMgmt = 0x8,  
    eExternalThreading        = 0x10,  
    eSelfAffectingThreading   = 0x20,  
    eSecurityInfrastructure   = 0x40,  
    eUI                       = 0x80,  
    eMayLeakOnAbort           = 0x100,  
    eAll                      = 0x1ff  
} EHostProtectionCategories;  
```  
  
## <a name="members"></a><span data-ttu-id="a0fbd-105">Member</span><span class="sxs-lookup"><span data-stu-id="a0fbd-105">Members</span></span>  
  
|<span data-ttu-id="a0fbd-106">Member</span><span class="sxs-lookup"><span data-stu-id="a0fbd-106">Member</span></span>|<span data-ttu-id="a0fbd-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0fbd-107">Description</span></span>|  
|------------|-----------------|  
|`eAll`|<span data-ttu-id="a0fbd-108">Gibt an, dass alle verwalteten Klassen und Member, die von anderen abgedeckt werden `EApiCategories` Felder ausführen in teilweise vertrauenswürdigen Code blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="a0fbd-108">Specifies that all managed classes and members that are covered by other `EApiCategories` fields be blocked from running in partially trusted code.</span></span>|  
|`eExternalProcessMgmt`|<span data-ttu-id="a0fbd-109">Gibt an, dass verwaltete Klassen und Member, die die Erstellung, Bearbeitung und Löschung von externen Prozessen zu ermöglichen, an der Ausführung in teilweise vertrauenswürdigem Code gehindert werden.</span><span class="sxs-lookup"><span data-stu-id="a0fbd-109">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external processes be blocked from running in partially trusted code.</span></span>|  
|`eExternalThreading`|<span data-ttu-id="a0fbd-110">Gibt an, dass verwaltete Klassen und Member, mit denen die Erstellung, Bearbeitung und Zerstörung von externen Threads blockiert werden, Ausführen in teilweise vertrauenswürdigen Code.</span><span class="sxs-lookup"><span data-stu-id="a0fbd-110">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external threads be blocked from running in partially trusted code.</span></span>|  
|`eMayLeakOnAbort`|<span data-ttu-id="a0fbd-111">Gibt an, dass verwaltete Typen und Member, die möglicherweise bei Abbruch Speicherverlust könnte blockiert werden, Ausführen in teilweise vertrauenswürdigen Code.</span><span class="sxs-lookup"><span data-stu-id="a0fbd-111">Specifies that managed types and members that could potentially leak memory on abort be blocked from running in partially trusted code.</span></span>|  
|`eNoCategory`|<span data-ttu-id="a0fbd-112">Gibt an, dass keine Kategorien für verwalteten Code für die Ausführung in teilweise vertrauenswürdigem Code gehindert werden.</span><span class="sxs-lookup"><span data-stu-id="a0fbd-112">Specifies that no managed code categories be blocked from running in partially trusted code.</span></span>|  
|`eSecurityInfrastructure`|<span data-ttu-id="a0fbd-113">Gibt an, dass die common Language Runtime (CLR)-Security-Infrastruktur blockiert werden, von teilweise vertrauenswürdigem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a0fbd-113">Specifies that the common language runtime (CLR) security infrastructure be blocked from being used by partially trusted code.</span></span>|  
|`eSelfAffectingProcessMgmt`|<span data-ttu-id="a0fbd-114">Gibt an, dass verwaltete Klassen und Member, deren Funktionen gehosteten Prozess auswirken können, an der Ausführung in teilweise vertrauenswürdigem Code gehindert werden.</span><span class="sxs-lookup"><span data-stu-id="a0fbd-114">Specifies that managed classes and members whose capabilities can affect the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSelfAffectingThreading`|<span data-ttu-id="a0fbd-115">Gibt an, dass verwaltete Klassen und Member, deren Funktionen Threads im Prozess gehosteten auswirken können, an der Ausführung in teilweise vertrauenswürdigem Code gehindert werden.</span><span class="sxs-lookup"><span data-stu-id="a0fbd-115">Specifies that managed classes and members whose capabilities can affect threads in the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSharedState`|<span data-ttu-id="a0fbd-116">Gibt an, dass verwaltete Klassen und Member, die gemeinsam genutzten Zustand verfügbar zu machen, an der Ausführung in teilweise vertrauenswürdigem Code gehindert werden.</span><span class="sxs-lookup"><span data-stu-id="a0fbd-116">Specifies that managed classes and members that expose shared state be blocked from running in partially trusted code.</span></span>|  
|`eSynchronization`|<span data-ttu-id="a0fbd-117">Gibt an, dass die common Language Runtime-Klassen und Member, mit denen Benutzercode, der Sperren beibehält, an der Ausführung in teilweise vertrauenswürdigem Code gehindert werden.</span><span class="sxs-lookup"><span data-stu-id="a0fbd-117">Specifies that common language runtime classes and members that allow user code to hold locks be blocked from running in partially trusted code.</span></span>|  
|`eUI`|<span data-ttu-id="a0fbd-118">Gibt an, dass verwaltete Klassen und Member, die zulassen, oder erfordern menschliche Interaktion ausführen in teilweise vertrauenswürdigen Code blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="a0fbd-118">Specifies that managed classes and members that allow or require human interaction be blocked from running in partially trusted code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0fbd-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a0fbd-119">Remarks</span></span>  
 <span data-ttu-id="a0fbd-120">Die [ICLRHostProtectionManager:: SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) Methode nimmt einen Parameter vom Typ `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="a0fbd-120">The [ICLRHostProtectionManager::SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) method takes a parameter of type `EApiCategories`.</span></span>  
  
 <span data-ttu-id="a0fbd-121">Die `EApiCategories` Enumeration und die `SetProtectedCategories` Methode beziehen sich direkt an die verwaltete <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> Klasse.</span><span class="sxs-lookup"><span data-stu-id="a0fbd-121">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="a0fbd-122">Die verwaltete Klasse wird verwendet, mit der <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> -Enumeration, deren Werte direkt entsprechen der `EApiCategories` -Werten, um verwaltete Typen und Member, die Funktionen von beschriebenen Kategorien verfügbar machen `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="a0fbd-122">The managed class is used with the <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumeration, whose values correspond directly to the `EApiCategories` values, to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0fbd-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a0fbd-123">Requirements</span></span>  
 <span data-ttu-id="a0fbd-124">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0fbd-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0fbd-125">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a0fbd-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a0fbd-126">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a0fbd-126">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="a0fbd-127">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="a0fbd-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a0fbd-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0fbd-128">See also</span></span>

- [<span data-ttu-id="a0fbd-129">ICLRHostProtectionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0fbd-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="a0fbd-130">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="a0fbd-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
