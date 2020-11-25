---
title: CorDebugGCType-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugGCType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGCType
helpviewer_keywords:
- CorDebugGCType enumeration [.NET Framework debugging]
ms.assetid: 880ca92a-42d4-42a5-9b9c-c2848eb39c6a
topic_type:
- apiref
ms.openlocfilehash: 6b3075613af0403527ecf67d574c0f5733a5cd8b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712611"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="48ec4-102">CorDebugGCType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="48ec4-102">CorDebugGCType Enumeration</span></span>

<span data-ttu-id="48ec4-103">Gibt an, ob die Garbage Collection auf einer Arbeitsstation oder einen Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="48ec4-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48ec4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="48ec4-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="48ec4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="48ec4-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="48ec4-106">Member</span><span class="sxs-lookup"><span data-stu-id="48ec4-106">Members</span></span>  
  
|<span data-ttu-id="48ec4-107">Membername</span><span class="sxs-lookup"><span data-stu-id="48ec4-107">Member name</span></span>|<span data-ttu-id="48ec4-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48ec4-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="48ec4-109">Der Garbage Collector wird auf einer Arbeitsstation ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="48ec4-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="48ec4-110">Der Garbage Collector wird auf einem Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="48ec4-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48ec4-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="48ec4-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48ec4-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="48ec4-112">Requirements</span></span>  

 <span data-ttu-id="48ec4-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48ec4-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48ec4-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48ec4-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48ec4-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48ec4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48ec4-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48ec4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48ec4-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="48ec4-117">See also</span></span>

- [<span data-ttu-id="48ec4-118">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="48ec4-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
