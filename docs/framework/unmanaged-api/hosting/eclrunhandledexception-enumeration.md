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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e5fb3ab1d2dedb220fd4a486409512414233021
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176669"
---
# <a name="eclrunhandledexception-enumeration"></a><span data-ttu-id="4316c-102">EClrUnhandledException-Enumeration</span><span class="sxs-lookup"><span data-stu-id="4316c-102">EClrUnhandledException Enumeration</span></span>
<span data-ttu-id="4316c-103">Beschreibt die verfügbaren Optionen für die Verwaltung von Ausnahmen, die in Benutzercode nicht behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="4316c-103">Describes the available options for managing exceptions that are unhandled in user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4316c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4316c-104">Syntax</span></span>  
  
```  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a><span data-ttu-id="4316c-105">Member</span><span class="sxs-lookup"><span data-stu-id="4316c-105">Members</span></span>  
  
|<span data-ttu-id="4316c-106">Member</span><span class="sxs-lookup"><span data-stu-id="4316c-106">Member</span></span>|<span data-ttu-id="4316c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4316c-107">Description</span></span>|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|<span data-ttu-id="4316c-108">Gibt an, dass das Standardverhalten auftritt.</span><span class="sxs-lookup"><span data-stu-id="4316c-108">Specifies that the default behavior occurs.</span></span> <span data-ttu-id="4316c-109">Der Prozess wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="4316c-109">The process is torn down.</span></span>|  
|`eHostDeterminedPolicy`|<span data-ttu-id="4316c-110">Gibt an, dass die common Language Runtime (CLR) nicht behandelte Ausnahmen ignoriert und kann der Host weitere Aktion zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="4316c-110">Specifies that the common language runtime (CLR) ignores unhandled exceptions and lets the host determine any further action.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4316c-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4316c-111">Remarks</span></span>  
 <span data-ttu-id="4316c-112">Verwenden, um anzugeben, dass die CLR verhält sich wie frühere Versionen der `eHostDeterminedPolicy` Member.</span><span class="sxs-lookup"><span data-stu-id="4316c-112">To specify that the CLR behave like earlier versions, use the `eHostDeterminedPolicy` member.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4316c-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4316c-113">Requirements</span></span>  
 <span data-ttu-id="4316c-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4316c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4316c-115">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4316c-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4316c-116">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4316c-116">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="4316c-117">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="4316c-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4316c-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4316c-118">See also</span></span>

- [<span data-ttu-id="4316c-119">EClrFailure-Enumeration</span><span class="sxs-lookup"><span data-stu-id="4316c-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="4316c-120">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="4316c-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="4316c-121">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4316c-121">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="4316c-122">SetUnhandledExceptionPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="4316c-122">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)
- [<span data-ttu-id="4316c-123">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4316c-123">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="4316c-124">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="4316c-124">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
