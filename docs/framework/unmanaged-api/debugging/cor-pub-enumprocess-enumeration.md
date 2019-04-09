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
ms.openlocfilehash: 02ff60852a85d003deb68cae96a184ac8d61c65f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089406"
---
# <a name="corpubenumprocess-enumeration"></a><span data-ttu-id="7fa73-102">COR_PUB_ENUMPROCESS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7fa73-102">COR_PUB_ENUMPROCESS Enumeration</span></span>
<span data-ttu-id="7fa73-103">Identifiziert den aufzulistenden Prozesstyp.</span><span class="sxs-lookup"><span data-stu-id="7fa73-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fa73-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7fa73-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="7fa73-105">Member</span><span class="sxs-lookup"><span data-stu-id="7fa73-105">Members</span></span>  
  
|<span data-ttu-id="7fa73-106">Membername</span><span class="sxs-lookup"><span data-stu-id="7fa73-106">Member name</span></span>|<span data-ttu-id="7fa73-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7fa73-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="7fa73-108">Ein verwalteter Prozess.</span><span class="sxs-lookup"><span data-stu-id="7fa73-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7fa73-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7fa73-109">Remarks</span></span>  
 <span data-ttu-id="7fa73-110">Die aktuelle Version von der nicht verwalteten Debug-API Listet nur verwaltete Prozesse.</span><span class="sxs-lookup"><span data-stu-id="7fa73-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fa73-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7fa73-111">Requirements</span></span>  
 <span data-ttu-id="7fa73-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fa73-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fa73-113">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="7fa73-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="7fa73-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7fa73-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="7fa73-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="7fa73-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7fa73-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7fa73-116">See also</span></span>

- [<span data-ttu-id="7fa73-117">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="7fa73-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
