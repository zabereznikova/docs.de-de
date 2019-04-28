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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 315d6dd522f3c6be2d36b1eb411d9f471350df60
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651752"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="3c63c-102">CorDebugGCType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="3c63c-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="3c63c-103">Gibt an, ob die Garbage Collection auf einer Arbeitsstation oder einen Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3c63c-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c63c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3c63c-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c63c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3c63c-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="3c63c-106">Member</span><span class="sxs-lookup"><span data-stu-id="3c63c-106">Members</span></span>  
  
|<span data-ttu-id="3c63c-107">Membername</span><span class="sxs-lookup"><span data-stu-id="3c63c-107">Member name</span></span>|<span data-ttu-id="3c63c-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3c63c-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="3c63c-109">Der Garbage Collector wird auf einer Arbeitsstation ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3c63c-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="3c63c-110">Der Garbage Collector wird auf einem Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3c63c-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c63c-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3c63c-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c63c-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3c63c-112">Requirements</span></span>  
 <span data-ttu-id="3c63c-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c63c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c63c-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c63c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c63c-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c63c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c63c-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c63c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c63c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c63c-117">See also</span></span>

- [<span data-ttu-id="3c63c-118">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="3c63c-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
