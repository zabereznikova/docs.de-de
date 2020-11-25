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
ms.openlocfilehash: 8350b507609e63c060cda08514200d386c37a6b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724324"
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="7d5b1-102">EInitializeNewDomainFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7d5b1-102">EInitializeNewDomainFlags Enumeration</span></span>

<span data-ttu-id="7d5b1-103">Ermöglicht dem Host, der Laufzeit Informationen zur Initialisierung einer Anwendungsdomäne bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="7d5b1-103">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d5b1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d5b1-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="7d5b1-105">Member</span><span class="sxs-lookup"><span data-stu-id="7d5b1-105">Members</span></span>  
  
|<span data-ttu-id="7d5b1-106">Member</span><span class="sxs-lookup"><span data-stu-id="7d5b1-106">Member</span></span>|<span data-ttu-id="7d5b1-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7d5b1-107">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="7d5b1-108">Keine Flags.</span><span class="sxs-lookup"><span data-stu-id="7d5b1-108">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="7d5b1-109">Informiert den Common Language Runtime (CLR), dass der Host keine Änderungen am Sicherheitszustand der Anwendungsdomäne in der-Methode vornimmt <xref:System.AppDomainManager.InitializeNewDomain%2A> .</span><span class="sxs-lookup"><span data-stu-id="7d5b1-109">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d5b1-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7d5b1-110">Remarks</span></span>  

 <span data-ttu-id="7d5b1-111">Die [iclrdomainmanager:: abtappdomainmanagertype](iclrdomainmanager-setappdomainmanagertype-method.md) -Methode nimmt einen Parameter vom Typ an `EInitializeNewDomainFlags` .</span><span class="sxs-lookup"><span data-stu-id="7d5b1-111">The [ICLRDomainManager::SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d5b1-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7d5b1-112">Requirements</span></span>  

 <span data-ttu-id="7d5b1-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d5b1-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d5b1-114">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="7d5b1-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7d5b1-115">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7d5b1-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d5b1-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d5b1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d5b1-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7d5b1-117">See also</span></span>

- [<span data-ttu-id="7d5b1-118">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="7d5b1-118">Hosting Enumerations</span></span>](hosting-enumerations.md)
- [<span data-ttu-id="7d5b1-119">SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="7d5b1-119">SetAppDomainManagerType Method</span></span>](iclrdomainmanager-setappdomainmanagertype-method.md)
