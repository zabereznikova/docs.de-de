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
ms.openlocfilehash: ec64f9bec0ee9b63796958b17c7f10b87692f1d0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686144"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a><span data-ttu-id="3453f-102">EHostBindingPolicyModifyFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="3453f-102">EHostBindingPolicyModifyFlags Enumeration</span></span>

<span data-ttu-id="3453f-103">Ermöglicht dem Host, die Art der Umleitung anzugeben, die Common Language Runtime (CLR) beim Anwenden von Richtlinien Änderungen von einer Quellassembly auf eine Zielassembly ausführen soll.</span><span class="sxs-lookup"><span data-stu-id="3453f-103">Allows the host to specify the type of redirection the common language runtime (CLR) should perform when applying policy modifications from a source assembly to a target assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3453f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3453f-104">Syntax</span></span>  
  
```cpp  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="3453f-105">Member</span><span class="sxs-lookup"><span data-stu-id="3453f-105">Members</span></span>  
  
|<span data-ttu-id="3453f-106">Member</span><span class="sxs-lookup"><span data-stu-id="3453f-106">Member</span></span>|<span data-ttu-id="3453f-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3453f-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|<span data-ttu-id="3453f-108">Gibt an, dass die CLR Richtlinien Werte der Quellassembly auf die der Zielassembly verkettet.</span><span class="sxs-lookup"><span data-stu-id="3453f-108">Specifies that the CLR will chain policy values of the source assembly onto those of the target assembly.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|<span data-ttu-id="3453f-109">Gibt an, dass die CLR die Standardaktion ausführt.</span><span class="sxs-lookup"><span data-stu-id="3453f-109">Specifies that the CLR will perform the default action.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|<span data-ttu-id="3453f-110">Gibt an, dass die CLR die Richtlinien Werte der Zielassembly auf die maximalen Werte festlegt.</span><span class="sxs-lookup"><span data-stu-id="3453f-110">Specifies that the CLR will set the policy values of the target assembly to the maximum values.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|<span data-ttu-id="3453f-111">Gibt an, dass die CLR Richtlinien Werte der Zielassembly durch die der Quellassembly ersetzen soll.</span><span class="sxs-lookup"><span data-stu-id="3453f-111">Specifies that the CLR will replace policy values of the target assembly with those of the source assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3453f-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3453f-112">Remarks</span></span>  

 <span data-ttu-id="3453f-113">Die [ICLRHostBindingPolicyManager:: ModifyApplicationPolicy](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) -Methode nimmt einen Parameter vom Typ an `EHostBindingPolicyModifyFlags` .</span><span class="sxs-lookup"><span data-stu-id="3453f-113">The [ICLRHostBindingPolicyManager::ModifyApplicationPolicy](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) method takes a parameter of type `EHostBindingPolicyModifyFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3453f-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3453f-114">Requirements</span></span>  

 <span data-ttu-id="3453f-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3453f-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3453f-116">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="3453f-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3453f-117">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3453f-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3453f-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3453f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3453f-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3453f-119">See also</span></span>

- [<span data-ttu-id="3453f-120">ICLRHostBindingPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3453f-120">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="3453f-121">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="3453f-121">Hosting Enumerations</span></span>](hosting-enumerations.md)
