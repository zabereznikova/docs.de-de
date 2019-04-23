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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9000f35e9a8f7ecc6c40cf0ef9c220fc9f4f9c10
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59185925"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="2f867-102">CustomDumpItem-Struktur</span><span class="sxs-lookup"><span data-stu-id="2f867-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="2f867-103">Beschreibt ein Element ein benutzerdefiniertes Speicherabbild in der Fehlerberichterstattung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="2f867-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f867-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2f867-104">Syntax</span></span>  
  
```  
struct {  
    ECustomDumpItemKind itemKind;   
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="2f867-105">Member</span><span class="sxs-lookup"><span data-stu-id="2f867-105">Members</span></span>  
  
|<span data-ttu-id="2f867-106">Member</span><span class="sxs-lookup"><span data-stu-id="2f867-106">Member</span></span>|<span data-ttu-id="2f867-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2f867-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="2f867-108">Ein [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) Wert, der die Art des hinzuzufügenden Elements angibt.</span><span class="sxs-lookup"><span data-stu-id="2f867-108">An [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="2f867-109">Derzeit nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="2f867-109">Not currently used.</span></span> <span data-ttu-id="2f867-110">Keine Elemente hinzugefügt, die Union müssen nicht größer als die Größe des Zeigers sein.</span><span class="sxs-lookup"><span data-stu-id="2f867-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="2f867-111">Wenn eine `struct` ist erforderlich, müssen Sie diese separat zugeordnet werden und darauf verweisen.</span><span class="sxs-lookup"><span data-stu-id="2f867-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f867-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2f867-112">Remarks</span></span>  
 <span data-ttu-id="2f867-113">[ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) nimmt einen Parameter vom Typ `CustomDumpItem`.</span><span class="sxs-lookup"><span data-stu-id="2f867-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f867-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2f867-114">Requirements</span></span>  
 <span data-ttu-id="2f867-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f867-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f867-116">**Header:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="2f867-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="2f867-117">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2f867-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2f867-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f867-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f867-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f867-119">See also</span></span>

- [<span data-ttu-id="2f867-120">Hosten von Strukturen</span><span class="sxs-lookup"><span data-stu-id="2f867-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
