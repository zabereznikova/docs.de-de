---
title: CustomDumpItem-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 47fd4e1dd3889cc7eeaa37457b47d9b2fd6dd8b5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="aca19-102">CustomDumpItem-Struktur</span><span class="sxs-lookup"><span data-stu-id="aca19-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="aca19-103">Beschreibt ein Element, das ein benutzerdefiniertes Speicherabbild Fehlerberichterstattung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="aca19-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aca19-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="aca19-104">Syntax</span></span>  
  
```  
struct {  
    ECustomDumpItemKind itemKind;   
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="aca19-105">Member</span><span class="sxs-lookup"><span data-stu-id="aca19-105">Members</span></span>  
  
|<span data-ttu-id="aca19-106">Member</span><span class="sxs-lookup"><span data-stu-id="aca19-106">Member</span></span>|<span data-ttu-id="aca19-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aca19-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="aca19-108">Ein [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) Wert, der die Art des hinzuzufügenden Elements angibt.</span><span class="sxs-lookup"><span data-stu-id="aca19-108">An [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="aca19-109">Zurzeit nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="aca19-109">Not currently used.</span></span> <span data-ttu-id="aca19-110">Keine Elemente hinzugefügt werden, auf die Union muss nicht größer als die Größe des Zeigers.</span><span class="sxs-lookup"><span data-stu-id="aca19-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="aca19-111">Wenn ein `struct` ist erforderlich, müssen Sie diese separat zugeordnet werden und zeigen Sie darauf.</span><span class="sxs-lookup"><span data-stu-id="aca19-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aca19-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aca19-112">Remarks</span></span>  
 <span data-ttu-id="aca19-113">[ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) akzeptiert einen Parameter vom Typ `CustomDumpItem`.</span><span class="sxs-lookup"><span data-stu-id="aca19-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aca19-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="aca19-114">Requirements</span></span>  
 <span data-ttu-id="aca19-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aca19-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aca19-116">**Header:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="aca19-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="aca19-117">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="aca19-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aca19-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aca19-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aca19-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aca19-119">See Also</span></span>  
 [<span data-ttu-id="aca19-120">Hosten von Strukturen</span><span class="sxs-lookup"><span data-stu-id="aca19-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
