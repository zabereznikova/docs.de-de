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
ms.openlocfilehash: 7ff10f84d8d270d31c5d560fb3c9bd3c81cf3e24
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616228"
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="af0af-102">EInitializeNewDomainFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="af0af-102">EInitializeNewDomainFlags Enumeration</span></span>
<span data-ttu-id="af0af-103">Ermöglicht dem Host, der Laufzeit Informationen zur Initialisierung einer Anwendungsdomäne bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="af0af-103">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af0af-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="af0af-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="af0af-105">Member</span><span class="sxs-lookup"><span data-stu-id="af0af-105">Members</span></span>  
  
|<span data-ttu-id="af0af-106">Member</span><span class="sxs-lookup"><span data-stu-id="af0af-106">Member</span></span>|<span data-ttu-id="af0af-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af0af-107">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="af0af-108">Keine Flags.</span><span class="sxs-lookup"><span data-stu-id="af0af-108">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="af0af-109">Informiert den Common Language Runtime (CLR), dass der Host keine Änderungen am Sicherheitszustand der Anwendungsdomäne in der-Methode vornimmt <xref:System.AppDomainManager.InitializeNewDomain%2A> .</span><span class="sxs-lookup"><span data-stu-id="af0af-109">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af0af-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="af0af-110">Remarks</span></span>  
 <span data-ttu-id="af0af-111">Die [iclrdomainmanager:: abtappdomainmanagertype](iclrdomainmanager-setappdomainmanagertype-method.md) -Methode nimmt einen Parameter vom Typ an `EInitializeNewDomainFlags` .</span><span class="sxs-lookup"><span data-stu-id="af0af-111">The [ICLRDomainManager::SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af0af-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="af0af-112">Requirements</span></span>  
 <span data-ttu-id="af0af-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af0af-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af0af-114">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="af0af-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="af0af-115">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="af0af-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="af0af-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af0af-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af0af-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af0af-117">See also</span></span>

- [<span data-ttu-id="af0af-118">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="af0af-118">Hosting Enumerations</span></span>](hosting-enumerations.md)
- [<span data-ttu-id="af0af-119">SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="af0af-119">SetAppDomainManagerType Method</span></span>](iclrdomainmanager-setappdomainmanagertype-method.md)
