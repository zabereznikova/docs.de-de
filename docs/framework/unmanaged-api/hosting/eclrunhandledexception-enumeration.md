---
title: EClrUnhandledException-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EClrUnhandledException
api_location: mscoree.dll
api_type: COM
f1_keywords: EClrUnhandledException
helpviewer_keywords: EClrUnhandledException enumeration [.NET Framework hosting]
ms.assetid: d231044e-2b53-4836-93f9-8117ff0e5c3a
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 67787072779e0cb22a339c2d13c972ba36f3ed61
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="eclrunhandledexception-enumeration"></a><span data-ttu-id="0b3c0-102">EClrUnhandledException-Enumeration</span><span class="sxs-lookup"><span data-stu-id="0b3c0-102">EClrUnhandledException Enumeration</span></span>
<span data-ttu-id="0b3c0-103">Beschreibt die verfügbaren Optionen zum Verwalten von Ausnahmen, die nicht vom Benutzercode behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="0b3c0-103">Describes the available options for managing exceptions that are unhandled in user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b3c0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b3c0-104">Syntax</span></span>  
  
```  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a><span data-ttu-id="0b3c0-105">Member</span><span class="sxs-lookup"><span data-stu-id="0b3c0-105">Members</span></span>  
  
|<span data-ttu-id="0b3c0-106">Member</span><span class="sxs-lookup"><span data-stu-id="0b3c0-106">Member</span></span>|<span data-ttu-id="0b3c0-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b3c0-107">Description</span></span>|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|<span data-ttu-id="0b3c0-108">Gibt an, dass das Standardverhalten erfolgt.</span><span class="sxs-lookup"><span data-stu-id="0b3c0-108">Specifies that the default behavior occurs.</span></span> <span data-ttu-id="0b3c0-109">Der Prozess wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="0b3c0-109">The process is torn down.</span></span>|  
|`eHostDeterminedPolicy`|<span data-ttu-id="0b3c0-110">Gibt an, dass die common Language Runtime (CLR) nicht behandelte Ausnahmen ignoriert und kann der Host weiteren Aktionen zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="0b3c0-110">Specifies that the common language runtime (CLR) ignores unhandled exceptions and lets the host determine any further action.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b3c0-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0b3c0-111">Remarks</span></span>  
 <span data-ttu-id="0b3c0-112">Verwenden, um anzugeben, dass die CLR Verhalten sich wie frühere Versionen der `eHostDeterminedPolicy` Member.</span><span class="sxs-lookup"><span data-stu-id="0b3c0-112">To specify that the CLR behave like earlier versions, use the `eHostDeterminedPolicy` member.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b3c0-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0b3c0-113">Requirements</span></span>  
 <span data-ttu-id="0b3c0-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b3c0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b3c0-115">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0b3c0-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0b3c0-116">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="0b3c0-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0b3c0-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b3c0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b3c0-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b3c0-118">See Also</span></span>  
 [<span data-ttu-id="0b3c0-119">EClrFailure-Enumeration</span><span class="sxs-lookup"><span data-stu-id="0b3c0-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="0b3c0-120">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="0b3c0-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="0b3c0-121">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0b3c0-121">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="0b3c0-122">SetUnhandledExceptionPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="0b3c0-122">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)  
 [<span data-ttu-id="0b3c0-123">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0b3c0-123">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [<span data-ttu-id="0b3c0-124">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="0b3c0-124">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
