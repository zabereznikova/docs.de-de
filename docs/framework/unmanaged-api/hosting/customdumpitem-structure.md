---
title: CustomDumpItem-Struktur
ms.date: 03/30/2017
api_name:
- CustomDumpItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CustomDumpItem
helpviewer_keywords:
- CustomDumpItem structure [.NET Framework hosting]
ms.assetid: fd9085ff-7beb-4c38-97f0-037cd8ba4f65
topic_type:
- apiref
ms.openlocfilehash: ae64edd8a3a628100d4c51d0b78be1bc8d49fc17
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138281"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="e8fae-102">CustomDumpItem-Struktur</span><span class="sxs-lookup"><span data-stu-id="e8fae-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="e8fae-103">Beschreibt ein Element, das einem benutzerdefinierten Dump in der Fehlerberichterstattung hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e8fae-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8fae-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e8fae-104">Syntax</span></span>  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;   
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="e8fae-105">Member</span><span class="sxs-lookup"><span data-stu-id="e8fae-105">Members</span></span>  
  
|<span data-ttu-id="e8fae-106">Member</span><span class="sxs-lookup"><span data-stu-id="e8fae-106">Member</span></span>|<span data-ttu-id="e8fae-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e8fae-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="e8fae-108">Ein [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) -Wert, der die Art des hinzu zufügenden Elements angibt.</span><span class="sxs-lookup"><span data-stu-id="e8fae-108">An [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="e8fae-109">Derzeit nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="e8fae-109">Not currently used.</span></span> <span data-ttu-id="e8fae-110">Alle Elemente, die der Union hinzugefügt werden, dürfen nicht größer als die Zeiger Größe sein.</span><span class="sxs-lookup"><span data-stu-id="e8fae-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="e8fae-111">Wenn eine `struct` erforderlich ist, müssen Sie Sie separat zuordnen und darauf verweisen.</span><span class="sxs-lookup"><span data-stu-id="e8fae-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8fae-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e8fae-112">Remarks</span></span>  
 <span data-ttu-id="e8fae-113">[ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) nimmt einen Parameter vom Typ `CustomDumpItem`an.</span><span class="sxs-lookup"><span data-stu-id="e8fae-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8fae-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e8fae-114">Requirements</span></span>  
 <span data-ttu-id="e8fae-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8fae-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8fae-116">**Header:** Mscoree. idl</span><span class="sxs-lookup"><span data-stu-id="e8fae-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="e8fae-117">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e8fae-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e8fae-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8fae-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8fae-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8fae-119">See also</span></span>

- [<span data-ttu-id="e8fae-120">Hosten von Strukturen</span><span class="sxs-lookup"><span data-stu-id="e8fae-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
