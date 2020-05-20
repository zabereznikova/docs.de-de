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
ms.openlocfilehash: d31b0190ef9a697fb27c849db080bec6c57618ae
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616384"
---
# <a name="eapicategories-enumeration"></a><span data-ttu-id="e9d86-102">EApiCategories-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e9d86-102">EApiCategories Enumeration</span></span>
<span data-ttu-id="e9d86-103">Beschreibt die Kategorien von Funktionen, die der Host für die Ausführung in teilweise vertrauenswürdigem Code blockieren kann.</span><span class="sxs-lookup"><span data-stu-id="e9d86-103">Describes the categories of capabilities that the host can block from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9d86-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9d86-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="e9d86-105">Member</span><span class="sxs-lookup"><span data-stu-id="e9d86-105">Members</span></span>  
  
|<span data-ttu-id="e9d86-106">Member</span><span class="sxs-lookup"><span data-stu-id="e9d86-106">Member</span></span>|<span data-ttu-id="e9d86-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9d86-107">Description</span></span>|  
|------------|-----------------|  
|`eAll`|<span data-ttu-id="e9d86-108">Gibt an, dass alle verwalteten Klassen und Member, die von anderen Feldern abgedeckt werden, `EApiCategories` in teilweise vertrauenswürdigem Code nicht ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="e9d86-108">Specifies that all managed classes and members that are covered by other `EApiCategories` fields be blocked from running in partially trusted code.</span></span>|  
|`eExternalProcessMgmt`|<span data-ttu-id="e9d86-109">Gibt an, dass verwaltete Klassen und Member, die das Erstellen, manipulieren und zerstören externer Prozesse zulassen, für die Ausführung in teilweise vertrauenswürdigem Code blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="e9d86-109">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external processes be blocked from running in partially trusted code.</span></span>|  
|`eExternalThreading`|<span data-ttu-id="e9d86-110">Gibt an, dass verwaltete Klassen und Member, die das Erstellen, manipulieren und löschen externer Threads zulassen, für die Ausführung in teilweise vertrauenswürdigem Code blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="e9d86-110">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external threads be blocked from running in partially trusted code.</span></span>|  
|`eMayLeakOnAbort`|<span data-ttu-id="e9d86-111">Gibt an, dass verwaltete Typen und Member, die ggf. beim Abbruch Speicher abbrechen können, in teilweise vertrauenswürdigem Code blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="e9d86-111">Specifies that managed types and members that could potentially leak memory on abort be blocked from running in partially trusted code.</span></span>|  
|`eNoCategory`|<span data-ttu-id="e9d86-112">Gibt an, dass die Ausführung von verwalteten Code Kategorien in teilweise vertrauenswürdigem Code nicht blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="e9d86-112">Specifies that no managed code categories be blocked from running in partially trusted code.</span></span>|  
|`eSecurityInfrastructure`|<span data-ttu-id="e9d86-113">Gibt an, dass die Common Language Runtime (CLR)-Sicherheitsinfrastruktur nicht von teilweise vertrauenswürdigem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e9d86-113">Specifies that the common language runtime (CLR) security infrastructure be blocked from being used by partially trusted code.</span></span>|  
|`eSelfAffectingProcessMgmt`|<span data-ttu-id="e9d86-114">Gibt an, dass verwaltete Klassen und Member, deren Funktionen den gehosteten Prozess beeinflussen können, in teilweise vertrauenswürdigem Code nicht ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="e9d86-114">Specifies that managed classes and members whose capabilities can affect the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSelfAffectingThreading`|<span data-ttu-id="e9d86-115">Gibt an, dass verwaltete Klassen und Member, deren Funktionen sich auf Threads im gehosteten Prozess auswirken können, in teilweise vertrauenswürdigem Code blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="e9d86-115">Specifies that managed classes and members whose capabilities can affect threads in the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSharedState`|<span data-ttu-id="e9d86-116">Gibt an, dass verwaltete Klassen und Member, die freigegebenen Zustand verfügbar machen, in teilweise vertrauenswürdigem Code blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="e9d86-116">Specifies that managed classes and members that expose shared state be blocked from running in partially trusted code.</span></span>|  
|`eSynchronization`|<span data-ttu-id="e9d86-117">Gibt an, dass Common Language Runtime Klassen und Member, die zulassen, dass Benutzercode Sperren enthalten, in teilweise vertrauenswürdigem Code blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="e9d86-117">Specifies that common language runtime classes and members that allow user code to hold locks be blocked from running in partially trusted code.</span></span>|  
|`eUI`|<span data-ttu-id="e9d86-118">Gibt an, dass verwaltete Klassen und Member, die eine Benutzerinteraktion zulassen oder erfordern, in teilweise vertrauenswürdigem Code blockiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e9d86-118">Specifies that managed classes and members that allow or require human interaction be blocked from running in partially trusted code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9d86-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e9d86-119">Remarks</span></span>  
 <span data-ttu-id="e9d86-120">Die [iclrhostschutzmanager:: SetProtectedCategories](iclrhostprotectionmanager-setprotectedcategories-method.md) -Methode nimmt einen Parameter vom Typ an `EApiCategories` .</span><span class="sxs-lookup"><span data-stu-id="e9d86-120">The [ICLRHostProtectionManager::SetProtectedCategories](iclrhostprotectionmanager-setprotectedcategories-method.md) method takes a parameter of type `EApiCategories`.</span></span>  
  
 <span data-ttu-id="e9d86-121">Die `EApiCategories` -Enumeration und die- `SetProtectedCategories` Methode sind direkt mit der verwalteten- <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> Klasse verknüpft.</span><span class="sxs-lookup"><span data-stu-id="e9d86-121">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="e9d86-122">Die verwaltete Klasse wird mit der- <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> Enumeration verwendet, deren Werte direkt den `EApiCategories` Werten entsprechen, um verwaltete Typen und Member zu markieren, die Funktionen verfügbar machen, die den in beschriebenen Kategorien entsprechen `EApiCategories` .</span><span class="sxs-lookup"><span data-stu-id="e9d86-122">The managed class is used with the <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumeration, whose values correspond directly to the `EApiCategories` values, to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9d86-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e9d86-123">Requirements</span></span>  
 <span data-ttu-id="e9d86-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9d86-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9d86-125">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="e9d86-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e9d86-126">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e9d86-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9d86-127">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9d86-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9d86-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9d86-128">See also</span></span>

- [<span data-ttu-id="e9d86-129">ICLRHostProtectionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e9d86-129">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="e9d86-130">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="e9d86-130">Hosting Enumerations</span></span>](hosting-enumerations.md)
