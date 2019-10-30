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
ms.openlocfilehash: 5e82f542bdc364a52fc558e582134a7d8d554ec3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131147"
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="c2a92-102">EContextType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c2a92-102">EContextType Enumeration</span></span>
<span data-ttu-id="c2a92-103">Beschreibt den Sicherheitskontext des aktuell ausgeführten Threads.</span><span class="sxs-lookup"><span data-stu-id="c2a92-103">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2a92-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c2a92-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="c2a92-105">Member</span><span class="sxs-lookup"><span data-stu-id="c2a92-105">Members</span></span>  
  
|<span data-ttu-id="c2a92-106">Member</span><span class="sxs-lookup"><span data-stu-id="c2a92-106">Member</span></span>|<span data-ttu-id="c2a92-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c2a92-107">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="c2a92-108">Gibt den Kontext des aktuellen Threads zu dem Zeitpunkt an, zu dem die Common Language Runtime (CLR) die [IHostSecurityManager:: GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) -Methode aufruft, oder den Kontext, der von der CLR in einem Aufruf von [IHostSecurityManager:: SetSecurityContext angefordert wird. ](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)-Methode.</span><span class="sxs-lookup"><span data-stu-id="c2a92-108">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="c2a92-109">Gibt einen Kontext an, über den der Host niedrigere Berechtigungen aufweist, z. b. die Garbage Collector oder die Klassen-oder Modulkonstruktoren.</span><span class="sxs-lookup"><span data-stu-id="c2a92-109">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2a92-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c2a92-110">Remarks</span></span>  
 <span data-ttu-id="c2a92-111">Die CLR stellt einen der `EContextType` Werte als Parameterwert in Aufrufen der Methoden `IHostSecurityManager::GetSecurityContext` und `IHostSecurityManager::SetSecurityContext` bereit.</span><span class="sxs-lookup"><span data-stu-id="c2a92-111">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2a92-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c2a92-112">Requirements</span></span>  
 <span data-ttu-id="c2a92-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2a92-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2a92-114">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="c2a92-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c2a92-115">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c2a92-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2a92-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2a92-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2a92-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2a92-117">See also</span></span>

- [<span data-ttu-id="c2a92-118">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c2a92-118">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="c2a92-119">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c2a92-119">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="c2a92-120">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="c2a92-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
