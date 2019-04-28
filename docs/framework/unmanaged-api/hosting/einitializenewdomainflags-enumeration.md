---
title: EInitializeNewDomainFlags-Enumeration
ms.date: 03/30/2017
api_name:
- EInitializeNewDomainFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EInitializeNewDomainFlags
helpviewer_keywords:
- EInitializeNewDomainFlags enumeration [.NET Framework hosting]
ms.assetid: 3a120ab2-f5ef-4c9b-8595-d3ed7247c342
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 04b0d9989d66888c33de0359e4c93529fcfbf8d1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61628625"
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="a7c87-102">EInitializeNewDomainFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="a7c87-102">EInitializeNewDomainFlags Enumeration</span></span>
<span data-ttu-id="a7c87-103">Kann der Host die Laufzeitumgebung mit Informationen zur Initialisierung einer Anwendungsdomäne bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a7c87-103">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7c87-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7c87-104">Syntax</span></span>  
  
```  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="a7c87-105">Member</span><span class="sxs-lookup"><span data-stu-id="a7c87-105">Members</span></span>  
  
|<span data-ttu-id="a7c87-106">Member</span><span class="sxs-lookup"><span data-stu-id="a7c87-106">Member</span></span>|<span data-ttu-id="a7c87-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7c87-107">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="a7c87-108">Keine Flags.</span><span class="sxs-lookup"><span data-stu-id="a7c87-108">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="a7c87-109">Informiert der common Language Runtime (CLR), dass der Host keine Änderungen an die Anwendungsdomäne, in den Sicherheitszustand vornehmen, wird die <xref:System.AppDomainManager.InitializeNewDomain%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="a7c87-109">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7c87-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a7c87-110">Remarks</span></span>  
 <span data-ttu-id="a7c87-111">Die [ICLRDomainManager:: SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) Methode nimmt einen Parameter vom Typ `EInitializeNewDomainFlags`.</span><span class="sxs-lookup"><span data-stu-id="a7c87-111">The [ICLRDomainManager::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7c87-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a7c87-112">Requirements</span></span>  
 <span data-ttu-id="a7c87-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7c87-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7c87-114">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a7c87-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a7c87-115">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a7c87-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a7c87-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7c87-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7c87-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7c87-117">See also</span></span>

- [<span data-ttu-id="a7c87-118">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="a7c87-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="a7c87-119">SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="a7c87-119">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)
