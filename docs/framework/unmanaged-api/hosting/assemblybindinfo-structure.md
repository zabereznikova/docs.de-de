---
title: AssemblyBindInfo-Struktur
ms.date: 03/30/2017
api_name:
- AssemblyBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyBindInfo
helpviewer_keywords:
- AssemblyBindInfo structure [.NET Framework hosting]
ms.assetid: 6fc01e98-c2e7-49de-ab9f-95937cc89017
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce79987c7fcf45b8d10dcc4613e053ee735941de
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59112813"
---
# <a name="assemblybindinfo-structure"></a><span data-ttu-id="b1732-102">AssemblyBindInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="b1732-102">AssemblyBindInfo Structure</span></span>
<span data-ttu-id="b1732-103">Enthält ausführliche Informationen über die referenzierte Assembly.</span><span class="sxs-lookup"><span data-stu-id="b1732-103">Provides detailed information about the referenced assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1732-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b1732-104">Syntax</span></span>  
  
```  
typedef struct _AssemblyBindInfo {  
    DWORD       dwAppDomainId;  
    LPCWSTR     lpReferencedIdentity;  
    LPCWSTR     lpPostPolicyIdentity;  
    DWORD       ePolicyLevel;  
} AssemblyBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="b1732-105">Member</span><span class="sxs-lookup"><span data-stu-id="b1732-105">Members</span></span>  
  
|<span data-ttu-id="b1732-106">Member</span><span class="sxs-lookup"><span data-stu-id="b1732-106">Member</span></span>|<span data-ttu-id="b1732-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1732-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="b1732-108">Ein eindeutiger Bezeichner für die `IStream` zurückgegeben, die durch einen Aufruf von [IHostAssemblyStore:: ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md), von dem die referenzierte Assembly geladen werden.</span><span class="sxs-lookup"><span data-stu-id="b1732-108">A unique identifier for the `IStream` returned by a call to [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md), from which the referenced assembly is to be loaded.</span></span>|  
|`lpReferencedIdentity`|<span data-ttu-id="b1732-109">Ein eindeutiger Bezeichner für die Assembly verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b1732-109">A unique identifier for the referenced assembly.</span></span>|  
|`lpPostPolicyIdentity`|<span data-ttu-id="b1732-110">Der Bezeichner für die referenzierte Assembly nach der Anwendung der Bindung Richtlinienwerte.</span><span class="sxs-lookup"><span data-stu-id="b1732-110">The identifier for the referenced assembly after the application of any binding policy values.</span></span>|  
|`ePolicyLevel`|<span data-ttu-id="b1732-111">Eines der [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) Werte, die angeben, welche versionsverwaltung-Richtlinien, sofern vorhanden, für die referenzierte Assembly angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b1732-111">One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that indicate which versioning policies, if any, should be applied to the referenced assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1732-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b1732-112">Remarks</span></span>  
 <span data-ttu-id="b1732-113">Der Host stellt den eindeutigen Bezeichner `dwAppDomainId` für die common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="b1732-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="b1732-114">Nach einem Aufruf von `IHostAssemblyStore::ProvideAssembly` zurückgegeben wird, die Runtime den Bezeichner verwendet, um zu bestimmen, ob der Inhalt des der `IStream` zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="b1732-114">After a call to `IHostAssemblyStore::ProvideAssembly` returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="b1732-115">Wenn dies der Fall ist, lädt die Runtime den Stream neu zuzuordnen, anstatt die vorhandene Kopie.</span><span class="sxs-lookup"><span data-stu-id="b1732-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="b1732-116">Die Common Language Runtime verwendet diesen Bezeichner auch als Suchschlüssel für Streams aus zurückgegebenen Aufrufe von [IHostAssemblyStore:: ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md).</span><span class="sxs-lookup"><span data-stu-id="b1732-116">The runtime also uses this identifier as a lookup key for streams returned from calls to [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md).</span></span> <span data-ttu-id="b1732-117">Aus diesem Grund muss der Bezeichner für Anforderungen zum modulimport und Anforderungen der Assembly eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="b1732-117">Therefore, the identifier must be unique for module requests and for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1732-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b1732-118">Requirements</span></span>  
 <span data-ttu-id="b1732-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1732-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1732-120">**Header:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="b1732-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="b1732-121">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b1732-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="b1732-122">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="b1732-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b1732-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1732-123">See also</span></span>

- [<span data-ttu-id="b1732-124">Hostingstrukturen</span><span class="sxs-lookup"><span data-stu-id="b1732-124">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="b1732-125">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b1732-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="b1732-126">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b1732-126">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="b1732-127">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b1732-127">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="b1732-128">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b1732-128">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="b1732-129">ModuleBindInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="b1732-129">ModuleBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)
