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
ms.openlocfilehash: 30a522fbf96aebaa96f33f4a1dc381683f183871
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726417"
---
# <a name="cor_pub_enumprocess-enumeration"></a><span data-ttu-id="81d3a-102">COR_PUB_ENUMPROCESS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="81d3a-102">COR_PUB_ENUMPROCESS Enumeration</span></span>

<span data-ttu-id="81d3a-103">Identifiziert den aufzulistenden Prozesstyp.</span><span class="sxs-lookup"><span data-stu-id="81d3a-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81d3a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="81d3a-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="81d3a-105">Member</span><span class="sxs-lookup"><span data-stu-id="81d3a-105">Members</span></span>  
  
|<span data-ttu-id="81d3a-106">Membername</span><span class="sxs-lookup"><span data-stu-id="81d3a-106">Member name</span></span>|<span data-ttu-id="81d3a-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="81d3a-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="81d3a-108">Ein verwalteter Prozess.</span><span class="sxs-lookup"><span data-stu-id="81d3a-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81d3a-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="81d3a-109">Remarks</span></span>  

 <span data-ttu-id="81d3a-110">Mit der aktuellen Version der nicht verwalteten Debug-API werden nur verwaltete Prozesse aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="81d3a-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81d3a-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="81d3a-111">Requirements</span></span>  

 <span data-ttu-id="81d3a-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81d3a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81d3a-113">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="81d3a-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="81d3a-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81d3a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81d3a-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81d3a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81d3a-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="81d3a-116">See also</span></span>

- [<span data-ttu-id="81d3a-117">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="81d3a-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
