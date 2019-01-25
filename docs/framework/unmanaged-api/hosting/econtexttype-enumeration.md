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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 635c232f2f6721e734f4fe6a74088fe9b82c6166
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54639470"
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="9670d-102">EContextType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="9670d-102">EContextType Enumeration</span></span>
<span data-ttu-id="9670d-103">Beschreibt den Sicherheitskontext des gerade ausgeführten Threads an.</span><span class="sxs-lookup"><span data-stu-id="9670d-103">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9670d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9670d-104">Syntax</span></span>  
  
```  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="9670d-105">Member</span><span class="sxs-lookup"><span data-stu-id="9670d-105">Members</span></span>  
  
|<span data-ttu-id="9670d-106">Member</span><span class="sxs-lookup"><span data-stu-id="9670d-106">Member</span></span>|<span data-ttu-id="9670d-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9670d-107">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="9670d-108">Gibt den Kontext des aktuellen Threads zum Zeitpunkt der common Language Runtime (CLR) Ruft die [IHostSecurityManager:: GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) Methode oder den Kontext, angefordert von der CLR in einem Aufruf der [ IHostSecurityManager:: SetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="9670d-108">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="9670d-109">Gibt einen Kontext an, über den geringeren Privilegien, z. B. der Garbage Collector oder Konstruktoren für Klasse oder das Modul auf dem Host ist.</span><span class="sxs-lookup"><span data-stu-id="9670d-109">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9670d-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9670d-110">Remarks</span></span>  
 <span data-ttu-id="9670d-111">Die CLR stellt eines der `EContextType` Werte als Parameterwert in Aufrufen an die `IHostSecurityManager::GetSecurityContext` und `IHostSecurityManager::SetSecurityContext` Methoden.</span><span class="sxs-lookup"><span data-stu-id="9670d-111">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9670d-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9670d-112">Requirements</span></span>  
 <span data-ttu-id="9670d-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9670d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9670d-114">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9670d-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9670d-115">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9670d-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9670d-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9670d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9670d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9670d-117">See also</span></span>
- [<span data-ttu-id="9670d-118">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9670d-118">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="9670d-119">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9670d-119">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="9670d-120">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="9670d-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
