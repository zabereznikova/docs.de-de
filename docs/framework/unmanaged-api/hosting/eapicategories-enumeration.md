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
ms.openlocfilehash: f25348410387a7b0e03ef897e8534336baeb126a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432208"
---
# <a name="eapicategories-enumeration"></a><span data-ttu-id="6acd5-102">EApiCategories-Enumeration</span><span class="sxs-lookup"><span data-stu-id="6acd5-102">EApiCategories Enumeration</span></span>
<span data-ttu-id="6acd5-103">Beschreibt die Kategorien von Funktionen, die der Host ausführen in teilweise vertrauenswürdigem Code blockieren kann.</span><span class="sxs-lookup"><span data-stu-id="6acd5-103">Describes the categories of capabilities that the host can block from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6acd5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6acd5-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="6acd5-105">Member</span><span class="sxs-lookup"><span data-stu-id="6acd5-105">Members</span></span>  
  
|<span data-ttu-id="6acd5-106">Member</span><span class="sxs-lookup"><span data-stu-id="6acd5-106">Member</span></span>|<span data-ttu-id="6acd5-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6acd5-107">Description</span></span>|  
|------------|-----------------|  
|`eAll`|<span data-ttu-id="6acd5-108">Gibt an, dass alle verwalteten Klassen und Member, die von anderen abgedeckt werden `EApiCategories` Felder gehindert werden in teilweise vertrauenswürdigem Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6acd5-108">Specifies that all managed classes and members that are covered by other `EApiCategories` fields be blocked from running in partially trusted code.</span></span>|  
|`eExternalProcessMgmt`|<span data-ttu-id="6acd5-109">Gibt an, dass verwaltete Klassen und Member, die Erstellung, Bearbeitung und Zerstörung von externen Prozessen ermöglichen, Ausführen in teilweise vertrauenswürdigem Code gesperrt werden.</span><span class="sxs-lookup"><span data-stu-id="6acd5-109">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external processes be blocked from running in partially trusted code.</span></span>|  
|`eExternalThreading`|<span data-ttu-id="6acd5-110">Gibt an, dass verwaltete Klassen und Member, die die Erstellung, Bearbeitung und Zerstörung von externen Threads ermöglichen ausführen in teilweise vertrauenswürdigem Code gesperrt werden.</span><span class="sxs-lookup"><span data-stu-id="6acd5-110">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external threads be blocked from running in partially trusted code.</span></span>|  
|`eMayLeakOnAbort`|<span data-ttu-id="6acd5-111">Gibt an, dass verwaltete Typen und Member, die beim Abbruch zu Speicherverlusten potenziell konnte ausführen in teilweise vertrauenswürdigem Code gesperrt werden.</span><span class="sxs-lookup"><span data-stu-id="6acd5-111">Specifies that managed types and members that could potentially leak memory on abort be blocked from running in partially trusted code.</span></span>|  
|`eNoCategory`|<span data-ttu-id="6acd5-112">Gibt an, dass keine Kategorien für verwalteten Code für die Ausführung in teilweise vertrauenswürdigem Code gehindert werden.</span><span class="sxs-lookup"><span data-stu-id="6acd5-112">Specifies that no managed code categories be blocked from running in partially trusted code.</span></span>|  
|`eSecurityInfrastructure`|<span data-ttu-id="6acd5-113">Gibt an, dass die common Language Runtime (CLR)-Security-Infrastruktur blockiert werden, von teilweise vertrauenswürdigem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6acd5-113">Specifies that the common language runtime (CLR) security infrastructure be blocked from being used by partially trusted code.</span></span>|  
|`eSelfAffectingProcessMgmt`|<span data-ttu-id="6acd5-114">Gibt an, dass verwaltete Klassen und Member, deren Funktionen gehosteten Prozess auswirken können, Ausführen in teilweise vertrauenswürdigem Code gesperrt werden.</span><span class="sxs-lookup"><span data-stu-id="6acd5-114">Specifies that managed classes and members whose capabilities can affect the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSelfAffectingThreading`|<span data-ttu-id="6acd5-115">Gibt an, dass verwaltete Klassen und Member, deren Funktionen Threads im gehosteten Prozess auswirken können, Ausführen in teilweise vertrauenswürdigem Code gesperrt werden.</span><span class="sxs-lookup"><span data-stu-id="6acd5-115">Specifies that managed classes and members whose capabilities can affect threads in the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSharedState`|<span data-ttu-id="6acd5-116">Gibt an, dass verwaltete Klassen und Member, die gemeinsam verwendete Zustände verfügbar machen ausführen in teilweise vertrauenswürdigem Code gesperrt werden.</span><span class="sxs-lookup"><span data-stu-id="6acd5-116">Specifies that managed classes and members that expose shared state be blocked from running in partially trusted code.</span></span>|  
|`eSynchronization`|<span data-ttu-id="6acd5-117">Gibt an, dass die common Language Runtime-Klassen und Member, mit die Benutzercode Sperren können ausführen in teilweise vertrauenswürdigem Code gesperrt werden.</span><span class="sxs-lookup"><span data-stu-id="6acd5-117">Specifies that common language runtime classes and members that allow user code to hold locks be blocked from running in partially trusted code.</span></span>|  
|`eUI`|<span data-ttu-id="6acd5-118">Gibt an, dass verwaltete Klassen und Member, die zugelassen oder erfordern menschliche Interaktion ausführen in teilweise vertrauenswürdigem Code gesperrt werden.</span><span class="sxs-lookup"><span data-stu-id="6acd5-118">Specifies that managed classes and members that allow or require human interaction be blocked from running in partially trusted code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6acd5-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6acd5-119">Remarks</span></span>  
 <span data-ttu-id="6acd5-120">Die [ICLRHostProtectionManager:: SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) Methode nimmt einen Parameter vom Typ `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="6acd5-120">The [ICLRHostProtectionManager::SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) method takes a parameter of type `EApiCategories`.</span></span>  
  
 <span data-ttu-id="6acd5-121">Die `EApiCategories` Enumeration und die `SetProtectedCategories` Methode beziehen sich direkt auf die verwaltete <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> Klasse.</span><span class="sxs-lookup"><span data-stu-id="6acd5-121">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="6acd5-122">Die verwaltete Klasse wird verwendet, mit der <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> Enumeration, deren Werte direkt entsprechen der `EApiCategories` Werte zu markieren von verwalteten Typen und Membern, die Funktionen, die Kategorien, die durch beschrieben entspricht verfügbar machen `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="6acd5-122">The managed class is used with the <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumeration, whose values correspond directly to the `EApiCategories` values, to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6acd5-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6acd5-123">Requirements</span></span>  
 <span data-ttu-id="6acd5-124">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6acd5-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6acd5-125">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6acd5-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6acd5-126">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="6acd5-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6acd5-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6acd5-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6acd5-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6acd5-128">See Also</span></span>  
 [<span data-ttu-id="6acd5-129">ICLRHostProtectionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6acd5-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [<span data-ttu-id="6acd5-130">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="6acd5-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
