---
title: EInitializeNewDomainFlags-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EInitializeNewDomainFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: EInitializeNewDomainFlags
helpviewer_keywords: EInitializeNewDomainFlags enumeration [.NET Framework hosting]
ms.assetid: 3a120ab2-f5ef-4c9b-8595-d3ed7247c342
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fa5c9aa050e0f5e634c43080d9caa5011a126529
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="6f71c-102">EInitializeNewDomainFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="6f71c-102">EInitializeNewDomainFlags Enumeration</span></span>
<span data-ttu-id="6f71c-103">Ermöglicht es dem Host die Laufzeit mit Informationen zur Initialisierung einer Anwendungsdomäne bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6f71c-103">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f71c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f71c-104">Syntax</span></span>  
  
```  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="6f71c-105">Member</span><span class="sxs-lookup"><span data-stu-id="6f71c-105">Members</span></span>  
  
|<span data-ttu-id="6f71c-106">Member</span><span class="sxs-lookup"><span data-stu-id="6f71c-106">Member</span></span>|<span data-ttu-id="6f71c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6f71c-107">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="6f71c-108">Keine Flags.</span><span class="sxs-lookup"><span data-stu-id="6f71c-108">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="6f71c-109">Informiert der common Language Runtime (CLR), dass der Host keine Änderungen an der Anwendungsdomäne, in den Sicherheitszustand vornehmen, wird die <xref:System.AppDomainManager.InitializeNewDomain%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="6f71c-109">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f71c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6f71c-110">Remarks</span></span>  
 <span data-ttu-id="6f71c-111">Die [ICLRDomainManager:: SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) Methode nimmt einen Parameter vom Typ `EInitializeNewDomainFlags`.</span><span class="sxs-lookup"><span data-stu-id="6f71c-111">The [ICLRDomainManager::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f71c-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6f71c-112">Requirements</span></span>  
 <span data-ttu-id="6f71c-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f71c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f71c-114">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6f71c-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6f71c-115">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="6f71c-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6f71c-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f71c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f71c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f71c-117">See Also</span></span>  
 [<span data-ttu-id="6f71c-118">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="6f71c-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
 [<span data-ttu-id="6f71c-119">SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="6f71c-119">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)
