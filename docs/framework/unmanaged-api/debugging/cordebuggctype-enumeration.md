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
ms.openlocfilehash: 6f4c96517375df4cd249b72953bf37812a498c0c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789363"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="6c18d-102">CorDebugGCType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="6c18d-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="6c18d-103">Gibt an, ob die Garbage Collection auf einer Arbeitsstation oder einen Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6c18d-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c18d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c18d-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c18d-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="6c18d-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="6c18d-106">Member</span><span class="sxs-lookup"><span data-stu-id="6c18d-106">Members</span></span>  
  
|<span data-ttu-id="6c18d-107">Mitgliedsname</span><span class="sxs-lookup"><span data-stu-id="6c18d-107">Member name</span></span>|<span data-ttu-id="6c18d-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c18d-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="6c18d-109">Der Garbage Collector wird auf einer Arbeitsstation ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6c18d-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="6c18d-110">Der Garbage Collector wird auf einem Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6c18d-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c18d-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6c18d-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c18d-112">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6c18d-112">Requirements</span></span>  
 <span data-ttu-id="6c18d-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c18d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c18d-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6c18d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6c18d-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c18d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c18d-116">**.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c18d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c18d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c18d-117">See also</span></span>

- [<span data-ttu-id="6c18d-118">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="6c18d-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
