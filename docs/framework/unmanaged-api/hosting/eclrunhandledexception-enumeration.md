---
title: EClrUnhandledException-Enumeration
ms.date: 03/30/2017
api_name:
- EClrUnhandledException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrUnhandledException
helpviewer_keywords:
- EClrUnhandledException enumeration [.NET Framework hosting]
ms.assetid: d231044e-2b53-4836-93f9-8117ff0e5c3a
topic_type:
- apiref
ms.openlocfilehash: 302db0d029b3811d151473323a7a60bd16a00ec1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131240"
---
# <a name="eclrunhandledexception-enumeration"></a><span data-ttu-id="a8bf1-102">EClrUnhandledException-Enumeration</span><span class="sxs-lookup"><span data-stu-id="a8bf1-102">EClrUnhandledException Enumeration</span></span>
<span data-ttu-id="a8bf1-103">Beschreibt die verfügbaren Optionen zum Verwalten von Ausnahmen, die im Benutzercode nicht behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="a8bf1-103">Describes the available options for managing exceptions that are unhandled in user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8bf1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a8bf1-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a><span data-ttu-id="a8bf1-105">Member</span><span class="sxs-lookup"><span data-stu-id="a8bf1-105">Members</span></span>  
  
|<span data-ttu-id="a8bf1-106">Member</span><span class="sxs-lookup"><span data-stu-id="a8bf1-106">Member</span></span>|<span data-ttu-id="a8bf1-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a8bf1-107">Description</span></span>|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|<span data-ttu-id="a8bf1-108">Gibt an, dass das Standardverhalten auftritt.</span><span class="sxs-lookup"><span data-stu-id="a8bf1-108">Specifies that the default behavior occurs.</span></span> <span data-ttu-id="a8bf1-109">Der Prozess wird beendet.</span><span class="sxs-lookup"><span data-stu-id="a8bf1-109">The process is torn down.</span></span>|  
|`eHostDeterminedPolicy`|<span data-ttu-id="a8bf1-110">Gibt an, dass die Common Language Runtime (CLR) nicht behandelte Ausnahmen ignoriert und der Host jede weitere Aktion bestimmen kann.</span><span class="sxs-lookup"><span data-stu-id="a8bf1-110">Specifies that the common language runtime (CLR) ignores unhandled exceptions and lets the host determine any further action.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8bf1-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a8bf1-111">Remarks</span></span>  
 <span data-ttu-id="a8bf1-112">Verwenden Sie das `eHostDeterminedPolicy`-Element, um anzugeben, dass die CLR sich wie frühere Versionen verhält.</span><span class="sxs-lookup"><span data-stu-id="a8bf1-112">To specify that the CLR behave like earlier versions, use the `eHostDeterminedPolicy` member.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8bf1-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a8bf1-113">Requirements</span></span>  
 <span data-ttu-id="a8bf1-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8bf1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8bf1-115">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="a8bf1-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a8bf1-116">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a8bf1-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a8bf1-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8bf1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8bf1-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8bf1-118">See also</span></span>

- [<span data-ttu-id="a8bf1-119">EClrFailure-Enumeration</span><span class="sxs-lookup"><span data-stu-id="a8bf1-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="a8bf1-120">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="a8bf1-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="a8bf1-121">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a8bf1-121">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="a8bf1-122">SetUnhandledExceptionPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="a8bf1-122">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)
- [<span data-ttu-id="a8bf1-123">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a8bf1-123">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="a8bf1-124">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="a8bf1-124">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
