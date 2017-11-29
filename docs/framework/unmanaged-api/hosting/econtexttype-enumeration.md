---
title: EContextType-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EContextType
api_location: mscoree.dll
api_type: COM
f1_keywords: EContextType
helpviewer_keywords: EContextType enumeration [.NET Framework hosting]
ms.assetid: 92b926a9-b87e-408a-9036-df7b752c9492
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 73e6e9a1f1118a524b86b3711c0c7a6af4777f2d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="b03a9-102">EContextType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b03a9-102">EContextType Enumeration</span></span>
<span data-ttu-id="b03a9-103">Beschreibt den Sicherheitskontext des aktuell ausgeführten Threads.</span><span class="sxs-lookup"><span data-stu-id="b03a9-103">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b03a9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b03a9-104">Syntax</span></span>  
  
```  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="b03a9-105">Member</span><span class="sxs-lookup"><span data-stu-id="b03a9-105">Members</span></span>  
  
|<span data-ttu-id="b03a9-106">Member</span><span class="sxs-lookup"><span data-stu-id="b03a9-106">Member</span></span>|<span data-ttu-id="b03a9-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b03a9-107">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="b03a9-108">Gibt den Kontext des aktuellen Threads zum Zeitpunkt der common Language Runtime (CLR) Ruft die [IHostSecurityManager:: GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) Methode oder den Kontext angefordert, die von der CLR in einem Aufruf der [ IHostSecurityManager:: SetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="b03a9-108">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="b03a9-109">Gibt einen Kontext, der über den vom Host mit geringeren Privilegien, z. B. die Garbage collection oder Klasse oder des Moduls Konstruktoren kann an.</span><span class="sxs-lookup"><span data-stu-id="b03a9-109">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b03a9-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b03a9-110">Remarks</span></span>  
 <span data-ttu-id="b03a9-111">Die CLR stellt eines der `EContextType` Werte als Parameterwert in Aufrufen an die `IHostSecurityManager::GetSecurityContext` und `IHostSecurityManager::SetSecurityContext` Methoden.</span><span class="sxs-lookup"><span data-stu-id="b03a9-111">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b03a9-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b03a9-112">Requirements</span></span>  
 <span data-ttu-id="b03a9-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b03a9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b03a9-114">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b03a9-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b03a9-115">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="b03a9-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b03a9-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b03a9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b03a9-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b03a9-117">See Also</span></span>  
 [<span data-ttu-id="b03a9-118">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b03a9-118">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="b03a9-119">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b03a9-119">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="b03a9-120">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="b03a9-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
