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
ms.openlocfilehash: 412e2bb7da7b5b3396342df169d56d2724ddb466
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740548"
---
# <a name="corpubenumprocess-enumeration"></a><span data-ttu-id="fd2b5-102">COR_PUB_ENUMPROCESS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="fd2b5-102">COR_PUB_ENUMPROCESS Enumeration</span></span>
<span data-ttu-id="fd2b5-103">Identifiziert den aufzulistenden Prozesstyp.</span><span class="sxs-lookup"><span data-stu-id="fd2b5-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd2b5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd2b5-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="fd2b5-105">Member</span><span class="sxs-lookup"><span data-stu-id="fd2b5-105">Members</span></span>  
  
|<span data-ttu-id="fd2b5-106">Membername</span><span class="sxs-lookup"><span data-stu-id="fd2b5-106">Member name</span></span>|<span data-ttu-id="fd2b5-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fd2b5-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="fd2b5-108">Ein verwalteter Prozess.</span><span class="sxs-lookup"><span data-stu-id="fd2b5-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd2b5-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fd2b5-109">Remarks</span></span>  
 <span data-ttu-id="fd2b5-110">Die aktuelle Version von der nicht verwalteten Debug-API Listet nur verwaltete Prozesse.</span><span class="sxs-lookup"><span data-stu-id="fd2b5-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd2b5-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fd2b5-111">Requirements</span></span>  
 <span data-ttu-id="fd2b5-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd2b5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd2b5-113">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="fd2b5-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="fd2b5-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd2b5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd2b5-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd2b5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd2b5-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd2b5-116">See also</span></span>

- [<span data-ttu-id="fd2b5-117">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="fd2b5-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
