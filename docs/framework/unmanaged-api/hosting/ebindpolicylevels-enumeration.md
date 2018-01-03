---
title: EBindPolicyLevels-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EBindPolicyLevels
api_location: mscoree.dll
api_type: COM
f1_keywords: EBindPolicyLevels
helpviewer_keywords: EBindPolicyLevels enumeration [.NET Framework hosting]
ms.assetid: a9e00b4f-b6d0-4257-bd88-4fe9af97b8fa
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 52e4d4522c7401aba198deed7853ccca71752d83
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ebindpolicylevels-enumeration"></a><span data-ttu-id="1285c-102">EBindPolicyLevels-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1285c-102">EBindPolicyLevels Enumeration</span></span>
<span data-ttu-id="1285c-103">Enthält Flags, um die Stufe der übernehmen oder Ändern der Assemblyrichtlinie für die anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1285c-103">Provides flags to specify the level at which to apply or modify assembly policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1285c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1285c-104">Syntax</span></span>  
  
```  
typedef enum {  
    ePolicyLevelNone         = 0x0,  
    ePolicyLevelRetargetable = 0x1,  
    ePolicyUnifiedToCLR      = 0x2,  
    ePolicyLevelApp          = 0x4,  
    ePolicyLevelPublisher    = 0x8,  
    ePolicyLevelHost         = 0x10,  
    ePolicyLevelAdmin        = 0x20  
    ePolicyPortability       = 0x40  
} EBindPolicyLevels;  
```  
  
## <a name="members"></a><span data-ttu-id="1285c-105">Member</span><span class="sxs-lookup"><span data-stu-id="1285c-105">Members</span></span>  
  
|<span data-ttu-id="1285c-106">Member</span><span class="sxs-lookup"><span data-stu-id="1285c-106">Member</span></span>|<span data-ttu-id="1285c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1285c-107">Description</span></span>|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|<span data-ttu-id="1285c-108">Gibt an, dass die Richtlinie auf Administratorebene angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1285c-108">Specifies that policy should be applied at the administrator level.</span></span>|  
|`ePolicyLevelApp`|<span data-ttu-id="1285c-109">Gibt an, dass die Richtlinie auf Anwendungsebene angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1285c-109">Specifies that policy should be applied at the application level.</span></span>|  
|`ePolicyLevelHost`|<span data-ttu-id="1285c-110">Gibt an, dass die Richtlinie auf der Hostebene angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1285c-110">Specifies that policy should be applied at the host level.</span></span>|  
|`ePolicyLevelNone`|<span data-ttu-id="1285c-111">Gibt keine Richtlinienebene Flags.</span><span class="sxs-lookup"><span data-stu-id="1285c-111">Specifies no policy-level flags.</span></span>|  
|`ePolicyLevelPublisher`|<span data-ttu-id="1285c-112">Gibt an, dass die Richtlinie auf den Verleger angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1285c-112">Specifies that policy should be applied at the publisher level.</span></span>|  
|`ePolicyLevelRetargetable`|<span data-ttu-id="1285c-113">Gibt an, dass die Richtlinie auf Variablen Ebenen angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1285c-113">Specifies that policy should be applicable at variable levels.</span></span>|  
|`ePolicyPortability`|<span data-ttu-id="1285c-114">Gibt an, dass die Richtlinie für Portabilität zwischen Implementierungen von .NET Framework-Assembly unterstützt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1285c-114">Specifies that policy should support portability between implementations of a .NET Framework assembly.</span></span> <span data-ttu-id="1285c-115">Finden Sie unter der [ \<SupportPortability >](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) Element für Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="1285c-115">See the [\<supportPortability>](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) configuration file element.</span></span>|  
|`ePolicyUnifiedToCLR`|<span data-ttu-id="1285c-116">Gibt an, dass die Richtlinie, die common Language Runtime (CLR) vereinheitlicht werden sollte.</span><span class="sxs-lookup"><span data-stu-id="1285c-116">Specifies that policy should be unified to that of the common language runtime (CLR).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1285c-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1285c-117">Remarks</span></span>  
 <span data-ttu-id="1285c-118">Diese Enumeration wird an Methoden übergeben der [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) Schnittstelle, um die Änderungen in Anwendungsrichtlinie angeben.</span><span class="sxs-lookup"><span data-stu-id="1285c-118">This enumeration is passed to methods of the [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) interface to specify changes in application policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1285c-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1285c-119">Requirements</span></span>  
 <span data-ttu-id="1285c-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1285c-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1285c-121">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1285c-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1285c-122">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="1285c-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1285c-123">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1285c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1285c-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1285c-124">See Also</span></span>  
 [<span data-ttu-id="1285c-125">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1285c-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="1285c-126">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="1285c-126">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
