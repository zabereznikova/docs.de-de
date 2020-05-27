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
ms.openlocfilehash: 31be0525c637e50c1161129277d651b56dadfaa3
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006752"
---
# <a name="modulebindinfo-structure"></a><span data-ttu-id="c61eb-102">ModuleBindInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="c61eb-102">ModuleBindInfo Structure</span></span>
<span data-ttu-id="c61eb-103">Bietet ausführliche Informationen über das Modul, auf das verwiesen wird, und die Assembly, die es enthält.</span><span class="sxs-lookup"><span data-stu-id="c61eb-103">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c61eb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c61eb-104">Syntax</span></span>  
  
```cpp  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="c61eb-105">Member</span><span class="sxs-lookup"><span data-stu-id="c61eb-105">Members</span></span>  
  
|<span data-ttu-id="c61eb-106">Member</span><span class="sxs-lookup"><span data-stu-id="c61eb-106">Member</span></span>|<span data-ttu-id="c61eb-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c61eb-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="c61eb-108">Ein eindeutiger Bezeichner für das-Element `IStream` , das durch einen Rückruf der [IHostAssemblyStore::P rovidemodule](ihostassemblystore-providemodule-method.md) -Methode zurückgegeben wird, aus der das Modul, auf das verwiesen wird, geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="c61eb-108">A unique identifier for the `IStream` that is returned by a call to the [IHostAssemblyStore::ProvideModule](ihostassemblystore-providemodule-method.md) method from which the referenced module is to be loaded.</span></span>|  
|`lpAssemblyIdentity`|<span data-ttu-id="c61eb-109">Ein eindeutiger Bezeichner der Assembly, die das Modul enthält, auf das verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="c61eb-109">A unique identifier for the assembly that contains the referenced module.</span></span>|  
|`lpModuleName`|<span data-ttu-id="c61eb-110">Der Name des Moduls, auf das verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="c61eb-110">The name of the referenced module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c61eb-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c61eb-111">Remarks</span></span>  
 <span data-ttu-id="c61eb-112">`ModuleBindInfo`wird als Parameter an übergeben `IHostAssemblyStore::ProvideModule` .</span><span class="sxs-lookup"><span data-stu-id="c61eb-112">`ModuleBindInfo` is passed as a parameter to `IHostAssemblyStore::ProvideModule`.</span></span> <span data-ttu-id="c61eb-113">Der Host stellt den eindeutigen Bezeichner `dwAppDomainId` für die Common Language Runtime (CLR) bereit.</span><span class="sxs-lookup"><span data-stu-id="c61eb-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="c61eb-114">Nachdem ein Aufrufen der [IHostAssemblyStore::P rovideassembly](ihostassemblystore-provideassembly-method.md) -Methode zurückgegeben wurde, verwendet die Common Language Runtime den Bezeichner, um zu bestimmen, ob der Inhalt der `IStream` zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="c61eb-114">After a call to the [IHostAssemblyStore::ProvideAssembly](ihostassemblystore-provideassembly-method.md) method returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="c61eb-115">Wenn dies der Fall ist, lädt die Laufzeit die vorhandene Kopie, anstatt den Stream neu zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="c61eb-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="c61eb-116">Die Laufzeit verwendet diesen Bezeichner auch als Suchschlüssel für Streams, die von Aufrufen der-Methode zurückgegeben werden `IHostAssemblyStore::ProvideAssembly` .</span><span class="sxs-lookup"><span data-stu-id="c61eb-116">The runtime also uses this identifier as a lookup key for streams that are returned from calls to the `IHostAssemblyStore::ProvideAssembly` method.</span></span> <span data-ttu-id="c61eb-117">Daher muss der Bezeichner für Modul Anforderungen und für Assemblyanforderungen eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="c61eb-117">Therefore, the identifier must be unique for module requests as well as for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c61eb-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c61eb-118">Requirements</span></span>  
 <span data-ttu-id="c61eb-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c61eb-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c61eb-120">**Header:** Mscoree. idl</span><span class="sxs-lookup"><span data-stu-id="c61eb-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="c61eb-121">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c61eb-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c61eb-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c61eb-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c61eb-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c61eb-123">See also</span></span>

- [<span data-ttu-id="c61eb-124">Hosten von Strukturen</span><span class="sxs-lookup"><span data-stu-id="c61eb-124">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="c61eb-125">AssemblyBindInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="c61eb-125">AssemblyBindInfo Structure</span></span>](assemblybindinfo-structure.md)
- [<span data-ttu-id="c61eb-126">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c61eb-126">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="c61eb-127">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c61eb-127">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="c61eb-128">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c61eb-128">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
