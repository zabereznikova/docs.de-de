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
ms.openlocfilehash: 94d2ec12309249afbecdc4130f8fe20c927b0a9b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616371"
---
# <a name="ebindpolicylevels-enumeration"></a><span data-ttu-id="c5f7d-102">EBindPolicyLevels-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c5f7d-102">EBindPolicyLevels Enumeration</span></span>
<span data-ttu-id="c5f7d-103">Stellt Flags bereit, um die Ebene anzugeben, auf der die Assemblyrichtlinie angewendet oder geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c5f7d-103">Provides flags to specify the level at which to apply or modify assembly policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5f7d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c5f7d-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="c5f7d-105">Member</span><span class="sxs-lookup"><span data-stu-id="c5f7d-105">Members</span></span>  
  
|<span data-ttu-id="c5f7d-106">Member</span><span class="sxs-lookup"><span data-stu-id="c5f7d-106">Member</span></span>|<span data-ttu-id="c5f7d-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c5f7d-107">Description</span></span>|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|<span data-ttu-id="c5f7d-108">Gibt an, dass die Richtlinie auf Administratorebene angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c5f7d-108">Specifies that policy should be applied at the administrator level.</span></span>|  
|`ePolicyLevelApp`|<span data-ttu-id="c5f7d-109">Gibt an, dass die Richtlinie auf Anwendungsebene angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c5f7d-109">Specifies that policy should be applied at the application level.</span></span>|  
|`ePolicyLevelHost`|<span data-ttu-id="c5f7d-110">Gibt an, dass die Richtlinie auf Hostebene angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c5f7d-110">Specifies that policy should be applied at the host level.</span></span>|  
|`ePolicyLevelNone`|<span data-ttu-id="c5f7d-111">Gibt keine Flags auf Richtlinien Ebene an.</span><span class="sxs-lookup"><span data-stu-id="c5f7d-111">Specifies no policy-level flags.</span></span>|  
|`ePolicyLevelPublisher`|<span data-ttu-id="c5f7d-112">Gibt an, dass die Richtlinie auf Verleger Ebene angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c5f7d-112">Specifies that policy should be applied at the publisher level.</span></span>|  
|`ePolicyLevelRetargetable`|<span data-ttu-id="c5f7d-113">Gibt an, dass die Richtlinie auf Variablen Ebenen anwendbar sein soll.</span><span class="sxs-lookup"><span data-stu-id="c5f7d-113">Specifies that policy should be applicable at variable levels.</span></span>|  
|`ePolicyPortability`|<span data-ttu-id="c5f7d-114">Gibt an, dass die Richtlinie die Portabilität zwischen Implementierungen einer .NET Framework Assembly unterstützen soll.</span><span class="sxs-lookup"><span data-stu-id="c5f7d-114">Specifies that policy should support portability between implementations of a .NET Framework assembly.</span></span> <span data-ttu-id="c5f7d-115">Weitere Informationen finden Sie unter [ \< supportportabili>](../../configure-apps/file-schema/runtime/supportportability-element.md) Konfigurationsdatei Element.</span><span class="sxs-lookup"><span data-stu-id="c5f7d-115">See the [\<supportPortability>](../../configure-apps/file-schema/runtime/supportportability-element.md) configuration file element.</span></span>|  
|`ePolicyUnifiedToCLR`|<span data-ttu-id="c5f7d-116">Gibt an, dass die Richtlinie für die Common Language Runtime (CLR) vereinheitlicht werden muss.</span><span class="sxs-lookup"><span data-stu-id="c5f7d-116">Specifies that policy should be unified to that of the common language runtime (CLR).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5f7d-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c5f7d-117">Remarks</span></span>  
 <span data-ttu-id="c5f7d-118">Diese Enumeration wird an Methoden der [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) -Schnittstelle übermittelt, um Änderungen an der Anwendungs Richtlinie anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c5f7d-118">This enumeration is passed to methods of the [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) interface to specify changes in application policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5f7d-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c5f7d-119">Requirements</span></span>  
 <span data-ttu-id="c5f7d-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5f7d-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5f7d-121">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="c5f7d-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c5f7d-122">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c5f7d-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c5f7d-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5f7d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5f7d-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5f7d-124">See also</span></span>

- [<span data-ttu-id="c5f7d-125">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5f7d-125">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="c5f7d-126">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="c5f7d-126">Hosting Enumerations</span></span>](hosting-enumerations.md)
