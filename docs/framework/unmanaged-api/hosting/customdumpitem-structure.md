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
ms.openlocfilehash: 154beef9398029f31dcb4d081019b9f292238af4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176473"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="b48d2-102">CustomDumpItem-Struktur</span><span class="sxs-lookup"><span data-stu-id="b48d2-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="b48d2-103">Beschreibt ein Element, das einem benutzerdefinierten Dump in der Fehlerberichterstattung hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b48d2-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b48d2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b48d2-104">Syntax</span></span>  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="b48d2-105">Members</span><span class="sxs-lookup"><span data-stu-id="b48d2-105">Members</span></span>  
  
|<span data-ttu-id="b48d2-106">Member</span><span class="sxs-lookup"><span data-stu-id="b48d2-106">Member</span></span>|<span data-ttu-id="b48d2-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b48d2-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="b48d2-108">Ein [ECustomDumpItemKind-Wert,](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) der die Art des hinzuzufügenden Elements angibt.</span><span class="sxs-lookup"><span data-stu-id="b48d2-108">An [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="b48d2-109">Derzeit nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="b48d2-109">Not currently used.</span></span> <span data-ttu-id="b48d2-110">Alle Elemente, die der Union hinzugefügt werden, dürfen nicht größer als die Zeigergröße sein.</span><span class="sxs-lookup"><span data-stu-id="b48d2-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="b48d2-111">Wenn `struct` a erforderlich ist, müssen Sie es separat zuweisen und darauf zeigen.</span><span class="sxs-lookup"><span data-stu-id="b48d2-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b48d2-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b48d2-112">Remarks</span></span>  
 <span data-ttu-id="b48d2-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) nimmt einen `CustomDumpItem`Parameter vom Typ an.</span><span class="sxs-lookup"><span data-stu-id="b48d2-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b48d2-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b48d2-114">Requirements</span></span>  
 <span data-ttu-id="b48d2-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b48d2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b48d2-116">**Kopfzeile:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="b48d2-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="b48d2-117">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b48d2-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b48d2-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b48d2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b48d2-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b48d2-119">See also</span></span>

- [<span data-ttu-id="b48d2-120">Hosten von Strukturen</span><span class="sxs-lookup"><span data-stu-id="b48d2-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
