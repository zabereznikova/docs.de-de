---
title: EClrFailure-Enumeration
ms.date: 03/30/2017
api_name:
- EClrFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrFailure
helpviewer_keywords:
- EClrFailure enumeration [.NET Framework hosting]
ms.assetid: 37b95cce-9bfb-4ecf-a00b-33dcba782c67
topic_type:
- apiref
ms.openlocfilehash: e07210203d8a8010890eeb511ff1c08821bfc4a7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616332"
---
# <a name="eclrfailure-enumeration"></a><span data-ttu-id="63ffe-102">EClrFailure-Enumeration</span><span class="sxs-lookup"><span data-stu-id="63ffe-102">EClrFailure Enumeration</span></span>
<span data-ttu-id="63ffe-103">Beschreibt den Satz von Fehlern, bei denen ein Host Richtlinien Aktionen festlegen kann.</span><span class="sxs-lookup"><span data-stu-id="63ffe-103">Describes the set of failures for which a host can set policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63ffe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="63ffe-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    FAIL_NonCriticalResource,  
    FAIL_CriticalResource,  
    FAIL_FatalRuntime,  
    FAIL_OrphanedLock  
    FAIL_StackOverflow  
    FAIL_AccessViolation  
    FAIL_CodeContract  
} EClrFailure;  
```  
  
## <a name="members"></a><span data-ttu-id="63ffe-105">Member</span><span class="sxs-lookup"><span data-stu-id="63ffe-105">Members</span></span>  
  
|<span data-ttu-id="63ffe-106">Member</span><span class="sxs-lookup"><span data-stu-id="63ffe-106">Member</span></span>|<span data-ttu-id="63ffe-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="63ffe-107">Description</span></span>|  
|------------|-----------------|  
|`FAIL_NonCriticalResource`|<span data-ttu-id="63ffe-108">Beim Versuch, eine Ressource (z. b. einen Thread, einen Speicherblock oder eine Sperre) in einem nicht kritischen Code Bereich zuzuordnen, ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="63ffe-108">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a non-critical region of code.</span></span>|  
|`FAIL_CriticalResource`|<span data-ttu-id="63ffe-109">Beim Versuch, eine Ressource (z. b. einen Thread, einen Speicherblock oder eine Sperre) in einem kritischen Code Bereich zuzuordnen, ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="63ffe-109">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a critical region of code.</span></span>|  
|`FAIL_FatalRuntime`|<span data-ttu-id="63ffe-110">Der Common Language Runtime (CLR) ist nicht mehr in der Lage, verwalteten Code im Prozess auszuführen.</span><span class="sxs-lookup"><span data-stu-id="63ffe-110">The common language runtime (CLR) is no longer able to run managed code in the process.</span></span> <span data-ttu-id="63ffe-111">Bei Aufrufen von-Hostingfunktionen wird ein HRESULT-Wert von HOST_E_CLRNOTAVAILABLE zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="63ffe-111">Henceforth, calls to any hosting functions return an HRESULT value of HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`FAIL_OrphanedLock`|<span data-ttu-id="63ffe-112">Ein Thread hat beim Zurückgeben eines Objekts eine Sperre nicht freigegeben <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="63ffe-112">A thread has failed to release a lock upon returning from an <xref:System.AppDomain> object.</span></span> <span data-ttu-id="63ffe-113">Dieser Fehler kann vom Host nicht festgelegt werden, damit ein Thread abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="63ffe-113">The host cannot set this failure to cause a thread to abort.</span></span>|  
|`FAIL_StackOverflow`|<span data-ttu-id="63ffe-114">Ein Stapelüberlauf ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="63ffe-114">A stack overflow has occurred.</span></span>|  
|`FAIL_AccessViolation`|<span data-ttu-id="63ffe-115">Es wurde versucht, geschützten Speicher zu lesen oder zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="63ffe-115">An attempt was made to read or write protected memory.</span></span> <span data-ttu-id="63ffe-116">Wird in der .NET Framework 4 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="63ffe-116">Not supported in the .NET Framework 4.</span></span>|  
|`FAIL_CodeContract`|<span data-ttu-id="63ffe-117">Ein Code Vertrags Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="63ffe-117">A code contract failure occurred.</span></span> <span data-ttu-id="63ffe-118">Siehe [Code Verträge](../../debug-trace-profile/code-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="63ffe-118">See [Code Contracts](../../debug-trace-profile/code-contracts.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63ffe-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="63ffe-119">Remarks</span></span>  
 <span data-ttu-id="63ffe-120">In der [ICLRPolicyManager:: abtactiononfailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) -Methode finden Sie eine Liste der [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) -Werte, mit denen der Host die Richtlinien Aktionen für Fehlerbedingungen angeben kann.</span><span class="sxs-lookup"><span data-stu-id="63ffe-120">See the [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) method for a list of [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values the host can use to specify the policy actions for failure conditions.</span></span> <span data-ttu-id="63ffe-121">Weitere Informationen zu kritischen und nicht kritischen Codebereichen finden Sie unter [eclroperations](eclroperation-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="63ffe-121">For more information about critical and non-critical regions of code, see [EClrOperation](eclroperation-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63ffe-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="63ffe-122">Requirements</span></span>  
 <span data-ttu-id="63ffe-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63ffe-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63ffe-124">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="63ffe-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="63ffe-125">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="63ffe-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="63ffe-126">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63ffe-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63ffe-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63ffe-127">See also</span></span>

- [<span data-ttu-id="63ffe-128">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="63ffe-128">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="63ffe-129">SetActionOnFailure-Methode</span><span class="sxs-lookup"><span data-stu-id="63ffe-129">SetActionOnFailure Method</span></span>](iclrpolicymanager-setactiononfailure-method.md)
- [<span data-ttu-id="63ffe-130">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="63ffe-130">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
- [<span data-ttu-id="63ffe-131">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="63ffe-131">Hosting Enumerations</span></span>](hosting-enumerations.md)
