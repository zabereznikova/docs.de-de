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
ms.openlocfilehash: 8dd070d2c895a94ac996be81e672bd67f59b83b7
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795897"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="de072-102">CorDebugGCType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="de072-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="de072-103">Gibt an, ob die Garbage Collection auf einer Arbeitsstation oder einen Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="de072-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de072-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="de072-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="de072-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="de072-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="de072-106">Member</span><span class="sxs-lookup"><span data-stu-id="de072-106">Members</span></span>  
  
|<span data-ttu-id="de072-107">Membername</span><span class="sxs-lookup"><span data-stu-id="de072-107">Member name</span></span>|<span data-ttu-id="de072-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="de072-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="de072-109">Der Garbage Collector wird auf einer Arbeitsstation ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="de072-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="de072-110">Der Garbage Collector wird auf einem Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="de072-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de072-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="de072-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de072-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="de072-112">Requirements</span></span>  
 <span data-ttu-id="de072-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de072-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de072-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de072-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de072-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de072-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de072-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de072-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de072-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="de072-117">See also</span></span>

- [<span data-ttu-id="de072-118">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="de072-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
