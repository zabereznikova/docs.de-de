---
title: ModuleBindInfo-Struktur
ms.date: 03/30/2017
api_name:
- ModuleBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ModuleBindInfo
helpviewer_keywords:
- ModuleBindInfo structure [.NET Framework hosting]
ms.assetid: 632d4adc-dbc9-4ce8-9397-abc3285c1c69
topic_type:
- apiref
ms.openlocfilehash: ae40d8adaae70ccff6e8058858a506267d58873f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133747"
---
# <a name="modulebindinfo-structure"></a><span data-ttu-id="f0c94-102">ModuleBindInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="f0c94-102">ModuleBindInfo Structure</span></span>
<span data-ttu-id="f0c94-103">Bietet ausführliche Informationen über das Modul, auf das verwiesen wird, und die Assembly, die es enthält.</span><span class="sxs-lookup"><span data-stu-id="f0c94-103">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0c94-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0c94-104">Syntax</span></span>  
  
```cpp  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="f0c94-105">Member</span><span class="sxs-lookup"><span data-stu-id="f0c94-105">Members</span></span>  
  
|<span data-ttu-id="f0c94-106">Member</span><span class="sxs-lookup"><span data-stu-id="f0c94-106">Member</span></span>|<span data-ttu-id="f0c94-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0c94-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="f0c94-108">Ein eindeutiger Bezeichner für die `IStream`, die durch einen [IHostAssemblyStore::P rovidemodule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) -Methode zurückgegeben wird, aus der das Modul, auf das verwiesen wird, geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="f0c94-108">A unique identifier for the `IStream` that is returned by a call to the [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) method from which the referenced module is to be loaded.</span></span>|  
|`lpAssemblyIdentity`|<span data-ttu-id="f0c94-109">Ein eindeutiger Bezeichner der Assembly, die das Modul enthält, auf das verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="f0c94-109">A unique identifier for the assembly that contains the referenced module.</span></span>|  
|`lpModuleName`|<span data-ttu-id="f0c94-110">Der Name des Moduls, auf das verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="f0c94-110">The name of the referenced module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0c94-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f0c94-111">Remarks</span></span>  
 <span data-ttu-id="f0c94-112">`ModuleBindInfo` wird als Parameter an `IHostAssemblyStore::ProvideModule`übergeben.</span><span class="sxs-lookup"><span data-stu-id="f0c94-112">`ModuleBindInfo` is passed as a parameter to `IHostAssemblyStore::ProvideModule`.</span></span> <span data-ttu-id="f0c94-113">Der Host stellt den eindeutigen Bezeichner `dwAppDomainId` für die Common Language Runtime (CLR) bereit.</span><span class="sxs-lookup"><span data-stu-id="f0c94-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="f0c94-114">Nachdem ein Aufrufen der [IHostAssemblyStore::P rovideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) -Methode zurückgegeben wurde, verwendet die Common Language Runtime den Bezeichner, um zu bestimmen, ob die Inhalte der `IStream` zugeordnet wurden.</span><span class="sxs-lookup"><span data-stu-id="f0c94-114">After a call to the [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) method returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="f0c94-115">Wenn dies der Fall ist, lädt die Laufzeit die vorhandene Kopie, anstatt den Stream neu zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="f0c94-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="f0c94-116">Die Laufzeit verwendet diesen Bezeichner auch als Suchschlüssel für Streams, die von Aufrufen der `IHostAssemblyStore::ProvideAssembly`-Methode zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f0c94-116">The runtime also uses this identifier as a lookup key for streams that are returned from calls to the `IHostAssemblyStore::ProvideAssembly` method.</span></span> <span data-ttu-id="f0c94-117">Daher muss der Bezeichner für Modul Anforderungen und für Assemblyanforderungen eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="f0c94-117">Therefore, the identifier must be unique for module requests as well as for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0c94-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f0c94-118">Requirements</span></span>  
 <span data-ttu-id="f0c94-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0c94-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0c94-120">**Header:** Mscoree. idl</span><span class="sxs-lookup"><span data-stu-id="f0c94-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="f0c94-121">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f0c94-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f0c94-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0c94-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0c94-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0c94-123">See also</span></span>

- [<span data-ttu-id="f0c94-124">Hosten von Strukturen</span><span class="sxs-lookup"><span data-stu-id="f0c94-124">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="f0c94-125">AssemblyBindInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="f0c94-125">AssemblyBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)
- [<span data-ttu-id="f0c94-126">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f0c94-126">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="f0c94-127">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f0c94-127">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="f0c94-128">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f0c94-128">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
