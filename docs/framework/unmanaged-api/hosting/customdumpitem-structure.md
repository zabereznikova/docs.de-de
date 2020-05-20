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
ms.openlocfilehash: 5c77a332593ba470d2e29b87cba182a770d5db7e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616436"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="7de5c-102">CustomDumpItem-Struktur</span><span class="sxs-lookup"><span data-stu-id="7de5c-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="7de5c-103">Beschreibt ein Element, das einem benutzerdefinierten Dump in der Fehlerberichterstattung hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7de5c-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7de5c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7de5c-104">Syntax</span></span>  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="7de5c-105">Member</span><span class="sxs-lookup"><span data-stu-id="7de5c-105">Members</span></span>  
  
|<span data-ttu-id="7de5c-106">Member</span><span class="sxs-lookup"><span data-stu-id="7de5c-106">Member</span></span>|<span data-ttu-id="7de5c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7de5c-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="7de5c-108">Ein [ECustomDumpItemKind](ecustomdumpitemkind-enumeration.md) -Wert, der die Art des hinzu zufügenden Elements angibt.</span><span class="sxs-lookup"><span data-stu-id="7de5c-108">An [ECustomDumpItemKind](ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="7de5c-109">Derzeit nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="7de5c-109">Not currently used.</span></span> <span data-ttu-id="7de5c-110">Alle Elemente, die der Union hinzugefügt werden, dürfen nicht größer als die Zeiger Größe sein.</span><span class="sxs-lookup"><span data-stu-id="7de5c-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="7de5c-111">Wenn eine `struct` erforderlich ist, müssen Sie Sie separat zuordnen und darauf verweisen.</span><span class="sxs-lookup"><span data-stu-id="7de5c-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7de5c-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7de5c-112">Remarks</span></span>  
 <span data-ttu-id="7de5c-113">[ICLRErrorReportingManager:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) nimmt einen Parameter vom Typ an `CustomDumpItem` .</span><span class="sxs-lookup"><span data-stu-id="7de5c-113">[ICLRErrorReportingManager::BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7de5c-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7de5c-114">Requirements</span></span>  
 <span data-ttu-id="7de5c-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7de5c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7de5c-116">**Header:** Mscoree. idl</span><span class="sxs-lookup"><span data-stu-id="7de5c-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="7de5c-117">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7de5c-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7de5c-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7de5c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7de5c-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7de5c-119">See also</span></span>

- [<span data-ttu-id="7de5c-120">Hostingstrukturen</span><span class="sxs-lookup"><span data-stu-id="7de5c-120">Hosting Structures</span></span>](hosting-structures.md)
