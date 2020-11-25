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
ms.openlocfilehash: a0992ca8ac4bfffef681c74de455a0eeb627a042
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726846"
---
# <a name="ebindpolicylevels-enumeration"></a><span data-ttu-id="cd011-102">EBindPolicyLevels-Enumeration</span><span class="sxs-lookup"><span data-stu-id="cd011-102">EBindPolicyLevels Enumeration</span></span>

<span data-ttu-id="cd011-103">Stellt Flags bereit, um die Ebene anzugeben, auf der die Assemblyrichtlinie angewendet oder geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="cd011-103">Provides flags to specify the level at which to apply or modify assembly policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd011-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cd011-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="cd011-105">Member</span><span class="sxs-lookup"><span data-stu-id="cd011-105">Members</span></span>  
  
|<span data-ttu-id="cd011-106">Member</span><span class="sxs-lookup"><span data-stu-id="cd011-106">Member</span></span>|<span data-ttu-id="cd011-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cd011-107">Description</span></span>|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|<span data-ttu-id="cd011-108">Gibt an, dass die Richtlinie auf Administratorebene angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="cd011-108">Specifies that policy should be applied at the administrator level.</span></span>|  
|`ePolicyLevelApp`|<span data-ttu-id="cd011-109">Gibt an, dass die Richtlinie auf Anwendungsebene angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="cd011-109">Specifies that policy should be applied at the application level.</span></span>|  
|`ePolicyLevelHost`|<span data-ttu-id="cd011-110">Gibt an, dass die Richtlinie auf Hostebene angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="cd011-110">Specifies that policy should be applied at the host level.</span></span>|  
|`ePolicyLevelNone`|<span data-ttu-id="cd011-111">Gibt keine Flags auf Richtlinien Ebene an.</span><span class="sxs-lookup"><span data-stu-id="cd011-111">Specifies no policy-level flags.</span></span>|  
|`ePolicyLevelPublisher`|<span data-ttu-id="cd011-112">Gibt an, dass die Richtlinie auf Verleger Ebene angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="cd011-112">Specifies that policy should be applied at the publisher level.</span></span>|  
|`ePolicyLevelRetargetable`|<span data-ttu-id="cd011-113">Gibt an, dass die Richtlinie auf Variablen Ebenen anwendbar sein soll.</span><span class="sxs-lookup"><span data-stu-id="cd011-113">Specifies that policy should be applicable at variable levels.</span></span>|  
|`ePolicyPortability`|<span data-ttu-id="cd011-114">Gibt an, dass die Richtlinie die Portabilität zwischen Implementierungen einer .NET Framework Assembly unterstützen soll.</span><span class="sxs-lookup"><span data-stu-id="cd011-114">Specifies that policy should support portability between implementations of a .NET Framework assembly.</span></span> <span data-ttu-id="cd011-115">Siehe das [\<supportPortability>](../../configure-apps/file-schema/runtime/supportportability-element.md) Element Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="cd011-115">See the [\<supportPortability>](../../configure-apps/file-schema/runtime/supportportability-element.md) configuration file element.</span></span>|  
|`ePolicyUnifiedToCLR`|<span data-ttu-id="cd011-116">Gibt an, dass die Richtlinie für die Common Language Runtime (CLR) vereinheitlicht werden muss.</span><span class="sxs-lookup"><span data-stu-id="cd011-116">Specifies that policy should be unified to that of the common language runtime (CLR).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd011-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cd011-117">Remarks</span></span>  

 <span data-ttu-id="cd011-118">Diese Enumeration wird an Methoden der [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) -Schnittstelle übermittelt, um Änderungen an der Anwendungs Richtlinie anzugeben.</span><span class="sxs-lookup"><span data-stu-id="cd011-118">This enumeration is passed to methods of the [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) interface to specify changes in application policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd011-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cd011-119">Requirements</span></span>  

 <span data-ttu-id="cd011-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd011-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd011-121">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="cd011-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cd011-122">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cd011-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd011-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd011-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd011-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cd011-124">See also</span></span>

- [<span data-ttu-id="cd011-125">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cd011-125">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="cd011-126">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="cd011-126">Hosting Enumerations</span></span>](hosting-enumerations.md)
