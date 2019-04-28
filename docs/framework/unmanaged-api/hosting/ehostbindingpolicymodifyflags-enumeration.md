---
title: EHostBindingPolicyModifyFlags-Enumeration
ms.date: 03/30/2017
api_name:
- EHostBindingPolicyModifyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EHostBindingPolicyModifyFlags
helpviewer_keywords:
- EHostBindingPolicyModifyFlags enumeration [.NET Framework hosting]
ms.assetid: 0339af16-ee1d-48ec-837d-a79d9a9c89f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e8357d20edba993f5a7682f31c04afea4362afd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796057"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a><span data-ttu-id="64404-102">EHostBindingPolicyModifyFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="64404-102">EHostBindingPolicyModifyFlags Enumeration</span></span>
<span data-ttu-id="64404-103">Ermöglicht dem Host an den Typ der Umleitung, die die common Language Runtime (CLR) durchführen sollten, wenn Änderungen der Richtlinie aus einer Assembly der Ereignisquelle in eine Zielassembly angewendet.</span><span class="sxs-lookup"><span data-stu-id="64404-103">Allows the host to specify the type of redirection the common language runtime (CLR) should perform when applying policy modifications from a source assembly to a target assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64404-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="64404-104">Syntax</span></span>  
  
```  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="64404-105">Member</span><span class="sxs-lookup"><span data-stu-id="64404-105">Members</span></span>  
  
|<span data-ttu-id="64404-106">Member</span><span class="sxs-lookup"><span data-stu-id="64404-106">Member</span></span>|<span data-ttu-id="64404-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="64404-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|<span data-ttu-id="64404-108">Gibt an, dass die CLR Richtlinienwerte der Quellassembly auf die der Zielassembly verkettet wird.</span><span class="sxs-lookup"><span data-stu-id="64404-108">Specifies that the CLR will chain policy values of the source assembly onto those of the target assembly.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|<span data-ttu-id="64404-109">Gibt an, dass die CLR die Standardaktion ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="64404-109">Specifies that the CLR will perform the default action.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|<span data-ttu-id="64404-110">Gibt an, dass die CLR die Richtlinienwerte der Zielassembly auf die maximalen Werte festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="64404-110">Specifies that the CLR will set the policy values of the target assembly to the maximum values.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|<span data-ttu-id="64404-111">Gibt an, dass die CLR Richtlinienwerte der Zielassembly mit denen der Quellassembly ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="64404-111">Specifies that the CLR will replace policy values of the target assembly with those of the source assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64404-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="64404-112">Remarks</span></span>  
 <span data-ttu-id="64404-113">Die [ICLRHostBindingPolicyManager:: ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) Methode nimmt einen Parameter vom Typ `EHostBindingPolicyModifyFlags`.</span><span class="sxs-lookup"><span data-stu-id="64404-113">The [ICLRHostBindingPolicyManager::ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) method takes a parameter of type `EHostBindingPolicyModifyFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64404-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="64404-114">Requirements</span></span>  
 <span data-ttu-id="64404-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64404-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64404-116">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="64404-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="64404-117">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="64404-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="64404-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64404-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64404-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64404-119">See also</span></span>

- [<span data-ttu-id="64404-120">ICLRHostBindingPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="64404-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="64404-121">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="64404-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
