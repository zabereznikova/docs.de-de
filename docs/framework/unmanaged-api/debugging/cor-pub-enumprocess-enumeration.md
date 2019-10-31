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
ms.openlocfilehash: f789105751ae2d498740ab60f326f9c0597483b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099212"
---
# <a name="cor_pub_enumprocess-enumeration"></a><span data-ttu-id="45a3b-102">COR_PUB_ENUMPROCESS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="45a3b-102">COR_PUB_ENUMPROCESS Enumeration</span></span>
<span data-ttu-id="45a3b-103">Identifiziert den aufzulistenden Prozesstyp.</span><span class="sxs-lookup"><span data-stu-id="45a3b-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45a3b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="45a3b-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="45a3b-105">Member</span><span class="sxs-lookup"><span data-stu-id="45a3b-105">Members</span></span>  
  
|<span data-ttu-id="45a3b-106">Membername</span><span class="sxs-lookup"><span data-stu-id="45a3b-106">Member name</span></span>|<span data-ttu-id="45a3b-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="45a3b-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="45a3b-108">Ein verwalteter Prozess.</span><span class="sxs-lookup"><span data-stu-id="45a3b-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45a3b-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="45a3b-109">Remarks</span></span>  
 <span data-ttu-id="45a3b-110">Mit der aktuellen Version der nicht verwalteten Debug-API werden nur verwaltete Prozesse aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="45a3b-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45a3b-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="45a3b-111">Requirements</span></span>  
 <span data-ttu-id="45a3b-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45a3b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45a3b-113">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="45a3b-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="45a3b-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45a3b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45a3b-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45a3b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45a3b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45a3b-116">See also</span></span>

- [<span data-ttu-id="45a3b-117">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="45a3b-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
