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
ms.openlocfilehash: c6d1ace12bd07fa1f14c8570eca1f950a5c22be9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686331"
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="12495-102">EContextType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="12495-102">EContextType Enumeration</span></span>

<span data-ttu-id="12495-103">Beschreibt den Sicherheitskontext des aktuell ausgeführten Threads.</span><span class="sxs-lookup"><span data-stu-id="12495-103">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12495-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="12495-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="12495-105">Member</span><span class="sxs-lookup"><span data-stu-id="12495-105">Members</span></span>  
  
|<span data-ttu-id="12495-106">Member</span><span class="sxs-lookup"><span data-stu-id="12495-106">Member</span></span>|<span data-ttu-id="12495-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="12495-107">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="12495-108">Gibt den Kontext des aktuellen Threads zu dem Zeitpunkt an, zu dem die Common Language Runtime (CLR) die [IHostSecurityManager:: GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md) -Methode aufruft, oder den Kontext, der von der CLR in einem Aufruf der [IHostSecurityManager:: SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) -Methode angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="12495-108">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="12495-109">Gibt einen Kontext an, über den der Host niedrigere Berechtigungen aufweist, z. b. die Garbage Collector oder die Klassen-oder Modulkonstruktoren.</span><span class="sxs-lookup"><span data-stu-id="12495-109">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12495-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="12495-110">Remarks</span></span>  

 <span data-ttu-id="12495-111">Die CLR liefert einen der `EContextType` -Werte als Parameterwert in Aufrufen der `IHostSecurityManager::GetSecurityContext` -Methode und der- `IHostSecurityManager::SetSecurityContext` Methode.</span><span class="sxs-lookup"><span data-stu-id="12495-111">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12495-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="12495-112">Requirements</span></span>  

 <span data-ttu-id="12495-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12495-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12495-114">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="12495-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="12495-115">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="12495-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="12495-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12495-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12495-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="12495-117">See also</span></span>

- [<span data-ttu-id="12495-118">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="12495-118">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="12495-119">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="12495-119">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="12495-120">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="12495-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
