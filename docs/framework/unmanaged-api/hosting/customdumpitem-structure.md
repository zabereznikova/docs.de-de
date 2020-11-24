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
ms.openlocfilehash: c77e93686c7d121e9fe2a92f03970404ab823dc0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673240"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="f4910-102">CustomDumpItem-Struktur</span><span class="sxs-lookup"><span data-stu-id="f4910-102">CustomDumpItem Structure</span></span>

<span data-ttu-id="f4910-103">Beschreibt ein Element, das einem benutzerdefinierten Dump in der Fehlerberichterstattung hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f4910-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4910-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f4910-104">Syntax</span></span>  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="f4910-105">Member</span><span class="sxs-lookup"><span data-stu-id="f4910-105">Members</span></span>  
  
|<span data-ttu-id="f4910-106">Member</span><span class="sxs-lookup"><span data-stu-id="f4910-106">Member</span></span>|<span data-ttu-id="f4910-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f4910-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="f4910-108">Ein [ECustomDumpItemKind](ecustomdumpitemkind-enumeration.md) -Wert, der die Art des hinzu zufügenden Elements angibt.</span><span class="sxs-lookup"><span data-stu-id="f4910-108">An [ECustomDumpItemKind](ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="f4910-109">Derzeit nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="f4910-109">Not currently used.</span></span> <span data-ttu-id="f4910-110">Alle Elemente, die der Union hinzugefügt werden, dürfen nicht größer als die Zeiger Größe sein.</span><span class="sxs-lookup"><span data-stu-id="f4910-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="f4910-111">Wenn eine `struct` erforderlich ist, müssen Sie Sie separat zuordnen und darauf verweisen.</span><span class="sxs-lookup"><span data-stu-id="f4910-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4910-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f4910-112">Remarks</span></span>  

 <span data-ttu-id="f4910-113">[ICLRErrorReportingManager:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) nimmt einen Parameter vom Typ an `CustomDumpItem` .</span><span class="sxs-lookup"><span data-stu-id="f4910-113">[ICLRErrorReportingManager::BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4910-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f4910-114">Requirements</span></span>  

 <span data-ttu-id="f4910-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4910-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4910-116">**Header:** Mscoree. idl</span><span class="sxs-lookup"><span data-stu-id="f4910-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="f4910-117">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f4910-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f4910-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4910-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4910-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f4910-119">See also</span></span>

- [<span data-ttu-id="f4910-120">Hosten von Strukturen</span><span class="sxs-lookup"><span data-stu-id="f4910-120">Hosting Structures</span></span>](hosting-structures.md)
