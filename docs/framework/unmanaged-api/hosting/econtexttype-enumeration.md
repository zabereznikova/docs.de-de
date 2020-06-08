---
title: EContextType-Enumeration
ms.date: 03/30/2017
api_name:
- EContextType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EContextType
helpviewer_keywords:
- EContextType enumeration [.NET Framework hosting]
ms.assetid: 92b926a9-b87e-408a-9036-df7b752c9492
topic_type:
- apiref
ms.openlocfilehash: b93b27957cc715a5b4718dd9ef61cd11f4a39914
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493401"
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="1f007-102">EContextType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1f007-102">EContextType Enumeration</span></span>
<span data-ttu-id="1f007-103">Beschreibt den Sicherheitskontext des aktuell ausgeführten Threads.</span><span class="sxs-lookup"><span data-stu-id="1f007-103">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f007-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1f007-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="1f007-105">Member</span><span class="sxs-lookup"><span data-stu-id="1f007-105">Members</span></span>  
  
|<span data-ttu-id="1f007-106">Member</span><span class="sxs-lookup"><span data-stu-id="1f007-106">Member</span></span>|<span data-ttu-id="1f007-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1f007-107">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="1f007-108">Gibt den Kontext des aktuellen Threads zu dem Zeitpunkt an, zu dem die Common Language Runtime (CLR) die [IHostSecurityManager:: GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md) -Methode aufruft, oder den Kontext, der von der CLR in einem Aufruf der [IHostSecurityManager:: SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) -Methode angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="1f007-108">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="1f007-109">Gibt einen Kontext an, über den der Host niedrigere Berechtigungen aufweist, z. b. die Garbage Collector oder die Klassen-oder Modulkonstruktoren.</span><span class="sxs-lookup"><span data-stu-id="1f007-109">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f007-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1f007-110">Remarks</span></span>  
 <span data-ttu-id="1f007-111">Die CLR liefert einen der `EContextType` -Werte als Parameterwert in Aufrufen der `IHostSecurityManager::GetSecurityContext` -Methode und der- `IHostSecurityManager::SetSecurityContext` Methode.</span><span class="sxs-lookup"><span data-stu-id="1f007-111">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f007-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1f007-112">Requirements</span></span>  
 <span data-ttu-id="1f007-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f007-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f007-114">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="1f007-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1f007-115">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="1f007-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1f007-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f007-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f007-117">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="1f007-117">See also</span></span>

- [<span data-ttu-id="1f007-118">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1f007-118">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="1f007-119">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1f007-119">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="1f007-120">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="1f007-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
