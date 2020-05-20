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
ms.openlocfilehash: 615637813b08629aaea74b23fa2737f52d61bafb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616917"
---
# <a name="assemblybindinfo-structure"></a><span data-ttu-id="3457a-102">AssemblyBindInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="3457a-102">AssemblyBindInfo Structure</span></span>
<span data-ttu-id="3457a-103">Bietet ausführliche Informationen über die Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="3457a-103">Provides detailed information about the referenced assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3457a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3457a-104">Syntax</span></span>  
  
```cpp  
typedef struct _AssemblyBindInfo {  
    DWORD       dwAppDomainId;  
    LPCWSTR     lpReferencedIdentity;  
    LPCWSTR     lpPostPolicyIdentity;  
    DWORD       ePolicyLevel;  
} AssemblyBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="3457a-105">Member</span><span class="sxs-lookup"><span data-stu-id="3457a-105">Members</span></span>  
  
|<span data-ttu-id="3457a-106">Member</span><span class="sxs-lookup"><span data-stu-id="3457a-106">Member</span></span>|<span data-ttu-id="3457a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3457a-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="3457a-108">Ein eindeutiger Bezeichner für das `IStream` , das durch einen [IHostAssemblyStore::P rovideassembly](ihostassemblystore-provideassembly-method.md)zurückgegeben wird, aus dem die referenzierte Assembly geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="3457a-108">A unique identifier for the `IStream` returned by a call to [IHostAssemblyStore::ProvideAssembly](ihostassemblystore-provideassembly-method.md), from which the referenced assembly is to be loaded.</span></span>|  
|`lpReferencedIdentity`|<span data-ttu-id="3457a-109">Eine eindeutige ID für die Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="3457a-109">A unique identifier for the referenced assembly.</span></span>|  
|`lpPostPolicyIdentity`|<span data-ttu-id="3457a-110">Der Bezeichner für die Assembly, auf die verwiesen wird, nach der Anwendung von Bindungs Richtlinien Werten.</span><span class="sxs-lookup"><span data-stu-id="3457a-110">The identifier for the referenced assembly after the application of any binding policy values.</span></span>|  
|`ePolicyLevel`|<span data-ttu-id="3457a-111">Einer der [EPolicyAction](epolicyaction-enumeration.md) -Werte, die angeben, welche Versions Verwaltungsrichtlinien ggf. auf die Assembly angewendet werden sollen, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="3457a-111">One of the [EPolicyAction](epolicyaction-enumeration.md) values that indicate which versioning policies, if any, should be applied to the referenced assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3457a-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3457a-112">Remarks</span></span>  
 <span data-ttu-id="3457a-113">Der Host stellt den eindeutigen Bezeichner `dwAppDomainId` für die Common Language Runtime (CLR) bereit.</span><span class="sxs-lookup"><span data-stu-id="3457a-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="3457a-114">Nachdem ein Rückruf `IHostAssemblyStore::ProvideAssembly` von zurückgegeben wurde, verwendet die Common Language Runtime den Bezeichner, um zu bestimmen, ob der Inhalt des `IStream` zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="3457a-114">After a call to `IHostAssemblyStore::ProvideAssembly` returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="3457a-115">Wenn dies der Fall ist, lädt die Laufzeit die vorhandene Kopie, anstatt den Stream neu zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="3457a-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="3457a-116">Die Laufzeit verwendet diesen Bezeichner auch als Suchschlüssel für Streams, die von Aufrufen an [IHostAssemblyStore::P rovidemodule](ihostassemblystore-providemodule-method.md)zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3457a-116">The runtime also uses this identifier as a lookup key for streams returned from calls to [IHostAssemblyStore::ProvideModule](ihostassemblystore-providemodule-method.md).</span></span> <span data-ttu-id="3457a-117">Daher muss der Bezeichner für Modul Anforderungen und für Assemblyanforderungen eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="3457a-117">Therefore, the identifier must be unique for module requests and for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3457a-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3457a-118">Requirements</span></span>  
 <span data-ttu-id="3457a-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3457a-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3457a-120">**Header:** Mscoree. idl</span><span class="sxs-lookup"><span data-stu-id="3457a-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="3457a-121">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3457a-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3457a-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3457a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3457a-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3457a-123">See also</span></span>

- [<span data-ttu-id="3457a-124">Hostingstrukturen</span><span class="sxs-lookup"><span data-stu-id="3457a-124">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="3457a-125">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3457a-125">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="3457a-126">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3457a-126">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="3457a-127">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3457a-127">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="3457a-128">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3457a-128">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="3457a-129">ModuleBindInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="3457a-129">ModuleBindInfo Structure</span></span>](modulebindinfo-structure.md)
