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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3109d5ba49b01f25c72aaa1c31c74984a683dd73
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746530"
---
# <a name="eclrfailure-enumeration"></a><span data-ttu-id="79246-102">EClrFailure-Enumeration</span><span class="sxs-lookup"><span data-stu-id="79246-102">EClrFailure Enumeration</span></span>
<span data-ttu-id="79246-103">Beschreibt die Fehler, die für die ein Host Richtlinienaktionen festlegen kann.</span><span class="sxs-lookup"><span data-stu-id="79246-103">Describes the set of failures for which a host can set policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79246-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="79246-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="79246-105">Member</span><span class="sxs-lookup"><span data-stu-id="79246-105">Members</span></span>  
  
|<span data-ttu-id="79246-106">Member</span><span class="sxs-lookup"><span data-stu-id="79246-106">Member</span></span>|<span data-ttu-id="79246-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="79246-107">Description</span></span>|  
|------------|-----------------|  
|`FAIL_NonCriticalResource`|<span data-ttu-id="79246-108">Fehler beim Versuch, eine Ressource (z. B. ein Thread, einen Speicherblock oder eine Sperre) reservieren in einen nicht-kritische Codebereich.</span><span class="sxs-lookup"><span data-stu-id="79246-108">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a non-critical region of code.</span></span>|  
|`FAIL_CriticalResource`|<span data-ttu-id="79246-109">Fehler beim Versuch, reservieren eine Ressource (z. B. ein Thread, einen Speicherblock oder eine Sperre) in einem kritischen Bereich des Codes.</span><span class="sxs-lookup"><span data-stu-id="79246-109">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a critical region of code.</span></span>|  
|`FAIL_FatalRuntime`|<span data-ttu-id="79246-110">Die common Language Runtime (CLR) ist nicht mehr in der Lage, verwalteten Code im Prozess ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="79246-110">The common language runtime (CLR) is no longer able to run managed code in the process.</span></span> <span data-ttu-id="79246-111">Damit geben Aufrufe alle Hostingfunktionen HOST_E_CLRNOTAVAILABLE einen HRESULT-Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="79246-111">Henceforth, calls to any hosting functions return an HRESULT value of HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`FAIL_OrphanedLock`|<span data-ttu-id="79246-112">Hat Fehler durch einen Thread eine Sperre nach dem Beenden einer <xref:System.AppDomain> Objekt.</span><span class="sxs-lookup"><span data-stu-id="79246-112">A thread has failed to release a lock upon returning from an <xref:System.AppDomain> object.</span></span> <span data-ttu-id="79246-113">Der Host kann nicht dazu, die dazu führen, dass einen Thread abgebrochen festlegen.</span><span class="sxs-lookup"><span data-stu-id="79246-113">The host cannot set this failure to cause a thread to abort.</span></span>|  
|`FAIL_StackOverflow`|<span data-ttu-id="79246-114">Es ist ein Stapelüberlauf aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="79246-114">A stack overflow has occurred.</span></span>|  
|`FAIL_AccessViolation`|<span data-ttu-id="79246-115">Es wurde versucht, das Lesen und Schreiben von geschütztem Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="79246-115">An attempt was made to read or write protected memory.</span></span> <span data-ttu-id="79246-116">Nicht unterstützt, die der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79246-116">Not supported in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>|  
|`FAIL_CodeContract`|<span data-ttu-id="79246-117">Ein Code-Contract-Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="79246-117">A code contract failure occurred.</span></span> <span data-ttu-id="79246-118">Finden Sie unter [Code Contracts](../../../../docs/framework/debug-trace-profile/code-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="79246-118">See [Code Contracts](../../../../docs/framework/debug-trace-profile/code-contracts.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79246-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="79246-119">Remarks</span></span>  
 <span data-ttu-id="79246-120">Finden Sie unter den [ICLRPolicyManager:: SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) -Methode für eine Liste der [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) Werte, die der Host kann mit der Aktionen für fehlerbedingungen an.</span><span class="sxs-lookup"><span data-stu-id="79246-120">See the [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) method for a list of [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values the host can use to specify the policy actions for failure conditions.</span></span> <span data-ttu-id="79246-121">Weitere Informationen zu wichtigen und nicht kritische Bereiche des Codes, finden Sie unter [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="79246-121">For more information about critical and non-critical regions of code, see [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79246-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="79246-122">Requirements</span></span>  
 <span data-ttu-id="79246-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79246-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79246-124">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="79246-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="79246-125">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="79246-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="79246-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79246-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79246-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79246-127">See also</span></span>
- [<span data-ttu-id="79246-128">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="79246-128">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="79246-129">SetActionOnFailure-Methode</span><span class="sxs-lookup"><span data-stu-id="79246-129">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)
- [<span data-ttu-id="79246-130">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="79246-130">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="79246-131">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="79246-131">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
