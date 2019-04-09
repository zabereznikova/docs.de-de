---
title: EBindPolicyLevels-Enumeration
ms.date: 03/30/2017
api_name:
- EBindPolicyLevels
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EBindPolicyLevels
helpviewer_keywords:
- EBindPolicyLevels enumeration [.NET Framework hosting]
ms.assetid: a9e00b4f-b6d0-4257-bd88-4fe9af97b8fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8f2b08662e719a3308a62ab5b60f5dc490f2a6a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142206"
---
# <a name="ebindpolicylevels-enumeration"></a><span data-ttu-id="3226a-102">EBindPolicyLevels-Enumeration</span><span class="sxs-lookup"><span data-stu-id="3226a-102">EBindPolicyLevels Enumeration</span></span>
<span data-ttu-id="3226a-103">Stellt Flags bereit, die Ebene angegeben, übernehmen oder Ändern von Assemblyrichtlinie an.</span><span class="sxs-lookup"><span data-stu-id="3226a-103">Provides flags to specify the level at which to apply or modify assembly policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3226a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3226a-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="3226a-105">Member</span><span class="sxs-lookup"><span data-stu-id="3226a-105">Members</span></span>  
  
|<span data-ttu-id="3226a-106">Member</span><span class="sxs-lookup"><span data-stu-id="3226a-106">Member</span></span>|<span data-ttu-id="3226a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3226a-107">Description</span></span>|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|<span data-ttu-id="3226a-108">Gibt an, dass die Richtlinie auf Administratorebene angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3226a-108">Specifies that policy should be applied at the administrator level.</span></span>|  
|`ePolicyLevelApp`|<span data-ttu-id="3226a-109">Gibt an, dass die Richtlinie auf Anwendungsebene angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3226a-109">Specifies that policy should be applied at the application level.</span></span>|  
|`ePolicyLevelHost`|<span data-ttu-id="3226a-110">Gibt an, dass die Richtlinie auf der Hostebene angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3226a-110">Specifies that policy should be applied at the host level.</span></span>|  
|`ePolicyLevelNone`|<span data-ttu-id="3226a-111">Gibt keine Flags für die Richtlinie auf Serverebene an.</span><span class="sxs-lookup"><span data-stu-id="3226a-111">Specifies no policy-level flags.</span></span>|  
|`ePolicyLevelPublisher`|<span data-ttu-id="3226a-112">Gibt an, dass die Richtlinie auf den Verleger angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3226a-112">Specifies that policy should be applied at the publisher level.</span></span>|  
|`ePolicyLevelRetargetable`|<span data-ttu-id="3226a-113">Gibt an, dass die Richtlinie auf Variablen Ebenen angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3226a-113">Specifies that policy should be applicable at variable levels.</span></span>|  
|`ePolicyPortability`|<span data-ttu-id="3226a-114">Gibt an, dass die Richtlinie für Portabilität zwischen Implementierungen von .NET Framework-Assembly unterstützen soll.</span><span class="sxs-lookup"><span data-stu-id="3226a-114">Specifies that policy should support portability between implementations of a .NET Framework assembly.</span></span> <span data-ttu-id="3226a-115">Finden Sie unter den [ \<SupportPortability >](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) Configuration File-Element.</span><span class="sxs-lookup"><span data-stu-id="3226a-115">See the [\<supportPortability>](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) configuration file element.</span></span>|  
|`ePolicyUnifiedToCLR`|<span data-ttu-id="3226a-116">Gibt an, dass die Richtlinie mit der common Language Runtime (CLR) vereinheitlicht werden sollte.</span><span class="sxs-lookup"><span data-stu-id="3226a-116">Specifies that policy should be unified to that of the common language runtime (CLR).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3226a-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3226a-117">Remarks</span></span>  
 <span data-ttu-id="3226a-118">Diese Enumeration wird zu Methoden zum Übergeben der [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) Schnittstelle, um die Änderungen in der Richtlinie für Anwendungen angeben.</span><span class="sxs-lookup"><span data-stu-id="3226a-118">This enumeration is passed to methods of the [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) interface to specify changes in application policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3226a-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3226a-119">Requirements</span></span>  
 <span data-ttu-id="3226a-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3226a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3226a-121">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3226a-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3226a-122">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3226a-122">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="3226a-123">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="3226a-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3226a-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3226a-124">See also</span></span>

- [<span data-ttu-id="3226a-125">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3226a-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="3226a-126">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="3226a-126">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
