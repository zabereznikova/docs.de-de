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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f14d3dcaad1cc8cac11599b1647d61df3a793301
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765179"
---
# <a name="modulebindinfo-structure"></a><span data-ttu-id="09351-102">ModuleBindInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="09351-102">ModuleBindInfo Structure</span></span>
<span data-ttu-id="09351-103">Enthält ausführliche Informationen über das Modul verwiesen wird und die Assembly, die sie enthält.</span><span class="sxs-lookup"><span data-stu-id="09351-103">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09351-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="09351-104">Syntax</span></span>  
  
```  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="09351-105">Member</span><span class="sxs-lookup"><span data-stu-id="09351-105">Members</span></span>  
  
|<span data-ttu-id="09351-106">Member</span><span class="sxs-lookup"><span data-stu-id="09351-106">Member</span></span>|<span data-ttu-id="09351-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09351-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="09351-108">Ein eindeutiger Bezeichner für die `IStream` zurückgegeben, die durch einen Aufruf der [IHostAssemblyStore:: ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) -Methode aus der das Modul verwiesen wird, ist geladen werden.</span><span class="sxs-lookup"><span data-stu-id="09351-108">A unique identifier for the `IStream` that is returned by a call to the [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) method from which the referenced module is to be loaded.</span></span>|  
|`lpAssemblyIdentity`|<span data-ttu-id="09351-109">Ein eindeutiger Bezeichner für die Assembly mit dem Modul verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="09351-109">A unique identifier for the assembly that contains the referenced module.</span></span>|  
|`lpModuleName`|<span data-ttu-id="09351-110">Der Name des Moduls auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="09351-110">The name of the referenced module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09351-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="09351-111">Remarks</span></span>  
 <span data-ttu-id="09351-112">`ModuleBindInfo` wird als Parameter übergeben, `IHostAssemblyStore::ProvideModule`.</span><span class="sxs-lookup"><span data-stu-id="09351-112">`ModuleBindInfo` is passed as a parameter to `IHostAssemblyStore::ProvideModule`.</span></span> <span data-ttu-id="09351-113">Der Host stellt den eindeutigen Bezeichner `dwAppDomainId` für die common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="09351-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="09351-114">Nach einem Aufruf von der [IHostAssemblyStore:: ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) Methode zurückgegeben wird, die Runtime den Bezeichner verwendet, um zu bestimmen, ob der Inhalt des der `IStream` zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="09351-114">After a call to the [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) method returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="09351-115">Wenn dies der Fall ist, lädt die Runtime den Stream neu zuzuordnen, anstatt die vorhandene Kopie.</span><span class="sxs-lookup"><span data-stu-id="09351-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="09351-116">Die Common Language Runtime verwendet diesen Bezeichner auch als Suchschlüssel für Datenströme, die von Aufrufen zurückgegeben werden die `IHostAssemblyStore::ProvideAssembly` Methode.</span><span class="sxs-lookup"><span data-stu-id="09351-116">The runtime also uses this identifier as a lookup key for streams that are returned from calls to the `IHostAssemblyStore::ProvideAssembly` method.</span></span> <span data-ttu-id="09351-117">Aus diesem Grund muss der Bezeichner für Anforderungen zum modulimport sowie für Anforderungen von Assembly eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="09351-117">Therefore, the identifier must be unique for module requests as well as for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09351-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="09351-118">Requirements</span></span>  
 <span data-ttu-id="09351-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09351-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09351-120">**Header:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="09351-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="09351-121">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="09351-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="09351-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09351-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09351-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09351-123">See also</span></span>

- [<span data-ttu-id="09351-124">Hosten von Strukturen</span><span class="sxs-lookup"><span data-stu-id="09351-124">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="09351-125">AssemblyBindInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="09351-125">AssemblyBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)
- [<span data-ttu-id="09351-126">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="09351-126">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="09351-127">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="09351-127">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="09351-128">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="09351-128">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
