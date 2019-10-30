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
ms.openlocfilehash: a2faf22b48dd0b809d6c3668a37f2119733a9b18
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129447"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a><span data-ttu-id="554a5-102">EHostBindingPolicyModifyFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="554a5-102">EHostBindingPolicyModifyFlags Enumeration</span></span>
<span data-ttu-id="554a5-103">Ermöglicht dem Host, die Art der Umleitung anzugeben, die Common Language Runtime (CLR) beim Anwenden von Richtlinien Änderungen von einer Quellassembly auf eine Zielassembly ausführen soll.</span><span class="sxs-lookup"><span data-stu-id="554a5-103">Allows the host to specify the type of redirection the common language runtime (CLR) should perform when applying policy modifications from a source assembly to a target assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="554a5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="554a5-104">Syntax</span></span>  
  
```cpp  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="554a5-105">Member</span><span class="sxs-lookup"><span data-stu-id="554a5-105">Members</span></span>  
  
|<span data-ttu-id="554a5-106">Member</span><span class="sxs-lookup"><span data-stu-id="554a5-106">Member</span></span>|<span data-ttu-id="554a5-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="554a5-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|<span data-ttu-id="554a5-108">Gibt an, dass die CLR Richtlinien Werte der Quellassembly auf die der Zielassembly verkettet.</span><span class="sxs-lookup"><span data-stu-id="554a5-108">Specifies that the CLR will chain policy values of the source assembly onto those of the target assembly.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|<span data-ttu-id="554a5-109">Gibt an, dass die CLR die Standardaktion ausführt.</span><span class="sxs-lookup"><span data-stu-id="554a5-109">Specifies that the CLR will perform the default action.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|<span data-ttu-id="554a5-110">Gibt an, dass die CLR die Richtlinien Werte der Zielassembly auf die maximalen Werte festlegt.</span><span class="sxs-lookup"><span data-stu-id="554a5-110">Specifies that the CLR will set the policy values of the target assembly to the maximum values.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|<span data-ttu-id="554a5-111">Gibt an, dass die CLR Richtlinien Werte der Zielassembly durch die der Quellassembly ersetzen soll.</span><span class="sxs-lookup"><span data-stu-id="554a5-111">Specifies that the CLR will replace policy values of the target assembly with those of the source assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="554a5-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="554a5-112">Remarks</span></span>  
 <span data-ttu-id="554a5-113">Die [ICLRHostBindingPolicyManager:: ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) -Methode nimmt einen Parameter vom Typ "`EHostBindingPolicyModifyFlags`" an.</span><span class="sxs-lookup"><span data-stu-id="554a5-113">The [ICLRHostBindingPolicyManager::ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) method takes a parameter of type `EHostBindingPolicyModifyFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="554a5-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="554a5-114">Requirements</span></span>  
 <span data-ttu-id="554a5-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="554a5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="554a5-116">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="554a5-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="554a5-117">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="554a5-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="554a5-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="554a5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="554a5-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="554a5-119">See also</span></span>

- [<span data-ttu-id="554a5-120">ICLRHostBindingPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="554a5-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="554a5-121">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="554a5-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
