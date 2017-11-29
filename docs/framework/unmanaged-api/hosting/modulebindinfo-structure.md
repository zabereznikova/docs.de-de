---
title: ModuleBindInfo-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ModuleBindInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: ModuleBindInfo
helpviewer_keywords: ModuleBindInfo structure [.NET Framework hosting]
ms.assetid: 632d4adc-dbc9-4ce8-9397-abc3285c1c69
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6488503e0300530b22c0c6f904e11db7f5d5b41c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="modulebindinfo-structure"></a><span data-ttu-id="352be-102">ModuleBindInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="352be-102">ModuleBindInfo Structure</span></span>
<span data-ttu-id="352be-103">Enthält ausführliche Informationen über das Modul verwiesen wird und die Assembly, die es enthält.</span><span class="sxs-lookup"><span data-stu-id="352be-103">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="352be-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="352be-104">Syntax</span></span>  
  
```  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="352be-105">Member</span><span class="sxs-lookup"><span data-stu-id="352be-105">Members</span></span>  
  
|<span data-ttu-id="352be-106">Member</span><span class="sxs-lookup"><span data-stu-id="352be-106">Member</span></span>|<span data-ttu-id="352be-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="352be-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="352be-108">Ein eindeutiger Bezeichner für die `IStream` zurückgegeben, die durch einen Aufruf der [IHostAssemblyStore:: ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) Methode, von dem das Modul verwiesen wird geladen werden.</span><span class="sxs-lookup"><span data-stu-id="352be-108">A unique identifier for the `IStream` that is returned by a call to the [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) method from which the referenced module is to be loaded.</span></span>|  
|`lpAssemblyIdentity`|<span data-ttu-id="352be-109">Ein eindeutiger Bezeichner für die Assembly, die das Modul verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="352be-109">A unique identifier for the assembly that contains the referenced module.</span></span>|  
|`lpModuleName`|<span data-ttu-id="352be-110">Der Name des Moduls auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="352be-110">The name of the referenced module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="352be-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="352be-111">Remarks</span></span>  
 <span data-ttu-id="352be-112">`ModuleBindInfo`wird als Parameter an übergeben `IHostAssemblyStore::ProvideModule`.</span><span class="sxs-lookup"><span data-stu-id="352be-112">`ModuleBindInfo` is passed as a parameter to `IHostAssemblyStore::ProvideModule`.</span></span> <span data-ttu-id="352be-113">Der Host stellt den eindeutigen Bezeichner `dwAppDomainId` für die common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="352be-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="352be-114">Nach einem Aufruf von der [IHostAssemblyStore:: ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) Methode zurückgegeben wird, die Laufzeit den Bezeichner verwendet, um zu bestimmen, ob der Inhalt des der `IStream` zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="352be-114">After a call to the [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) method returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="352be-115">Wenn dies der Fall ist, lädt die Common Language Runtime den Stream neu zuzuordnen, statt die vorhandene Kopie.</span><span class="sxs-lookup"><span data-stu-id="352be-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="352be-116">Die Common Language Runtime verwendet diesen Bezeichner auch als Suchschlüssel für Streams, die von Aufrufen zurückgegeben werden die `IHostAssemblyStore::ProvideAssembly` Methode.</span><span class="sxs-lookup"><span data-stu-id="352be-116">The runtime also uses this identifier as a lookup key for streams that are returned from calls to the `IHostAssemblyStore::ProvideAssembly` method.</span></span> <span data-ttu-id="352be-117">Aus diesem Grund muss der Bezeichner für Anforderungen zum modulimport als auch für Anforderungen der Assembly eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="352be-117">Therefore, the identifier must be unique for module requests as well as for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="352be-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="352be-118">Requirements</span></span>  
 <span data-ttu-id="352be-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="352be-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="352be-120">**Header:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="352be-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="352be-121">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="352be-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="352be-122">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="352be-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="352be-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="352be-123">See Also</span></span>  
 [<span data-ttu-id="352be-124">Hosten von Strukturen</span><span class="sxs-lookup"><span data-stu-id="352be-124">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [<span data-ttu-id="352be-125">AssemblyBindInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="352be-125">AssemblyBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)  
 [<span data-ttu-id="352be-126">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="352be-126">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="352be-127">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="352be-127">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="352be-128">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="352be-128">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
