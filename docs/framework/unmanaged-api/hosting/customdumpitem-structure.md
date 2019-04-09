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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59185925"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="55c1a-102">CustomDumpItem-Struktur</span><span class="sxs-lookup"><span data-stu-id="55c1a-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="55c1a-103">Beschreibt ein Element ein benutzerdefiniertes Speicherabbild in der Fehlerberichterstattung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="55c1a-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55c1a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="55c1a-104">Syntax</span></span>  
  
```  
struct {  
    ECustomDumpItemKind itemKind;   
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="55c1a-105">Member</span><span class="sxs-lookup"><span data-stu-id="55c1a-105">Members</span></span>  
  
|<span data-ttu-id="55c1a-106">Member</span><span class="sxs-lookup"><span data-stu-id="55c1a-106">Member</span></span>|<span data-ttu-id="55c1a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55c1a-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="55c1a-108">Ein [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) Wert, der die Art des hinzuzufügenden Elements angibt.</span><span class="sxs-lookup"><span data-stu-id="55c1a-108">An [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="55c1a-109">Derzeit nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="55c1a-109">Not currently used.</span></span> <span data-ttu-id="55c1a-110">Keine Elemente hinzugefügt, die Union müssen nicht größer als die Größe des Zeigers sein.</span><span class="sxs-lookup"><span data-stu-id="55c1a-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="55c1a-111">Wenn eine `struct` ist erforderlich, müssen Sie diese separat zugeordnet werden und darauf verweisen.</span><span class="sxs-lookup"><span data-stu-id="55c1a-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55c1a-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="55c1a-112">Remarks</span></span>  
 <span data-ttu-id="55c1a-113">[ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) nimmt einen Parameter vom Typ `CustomDumpItem`.</span><span class="sxs-lookup"><span data-stu-id="55c1a-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55c1a-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="55c1a-114">Requirements</span></span>  
 <span data-ttu-id="55c1a-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55c1a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55c1a-116">**Header:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="55c1a-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="55c1a-117">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="55c1a-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="55c1a-118">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="55c1a-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="55c1a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55c1a-119">See also</span></span>

- [<span data-ttu-id="55c1a-120">Hostingstrukturen</span><span class="sxs-lookup"><span data-stu-id="55c1a-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
