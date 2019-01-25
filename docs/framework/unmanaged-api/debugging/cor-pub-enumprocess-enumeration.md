---
title: COR_PUB_ENUMPROCESS-Enumeration
ms.date: 03/30/2017
api_name:
- COR_PUB_ENUMPROCESS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_PUB_ENUMPROCESS
helpviewer_keywords:
- COR_PUB_ENUMPROCESS enumeration [.NET Framework debugging]
ms.assetid: 5d3ada6e-feea-47da-a7ed-b664107c137f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bfc576e1b4f0bf1666dcd585a24dbfa398e9abde
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715854"
---
# <a name="corpubenumprocess-enumeration"></a><span data-ttu-id="e65db-102">COR_PUB_ENUMPROCESS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e65db-102">COR_PUB_ENUMPROCESS Enumeration</span></span>
<span data-ttu-id="e65db-103">Identifiziert den aufzulistenden Prozesstyp.</span><span class="sxs-lookup"><span data-stu-id="e65db-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e65db-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e65db-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="e65db-105">Member</span><span class="sxs-lookup"><span data-stu-id="e65db-105">Members</span></span>  
  
|<span data-ttu-id="e65db-106">Membername</span><span class="sxs-lookup"><span data-stu-id="e65db-106">Member name</span></span>|<span data-ttu-id="e65db-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e65db-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="e65db-108">Ein verwalteter Prozess.</span><span class="sxs-lookup"><span data-stu-id="e65db-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e65db-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e65db-109">Remarks</span></span>  
 <span data-ttu-id="e65db-110">Die aktuelle Version von der nicht verwalteten Debug-API Listet nur verwaltete Prozesse.</span><span class="sxs-lookup"><span data-stu-id="e65db-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e65db-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e65db-111">Requirements</span></span>  
 <span data-ttu-id="e65db-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e65db-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e65db-113">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="e65db-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="e65db-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e65db-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e65db-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e65db-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e65db-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e65db-116">See also</span></span>
- [<span data-ttu-id="e65db-117">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="e65db-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
