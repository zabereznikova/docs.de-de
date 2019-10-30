---
title: CorDebugHandleType-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugHandleType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugHandleType
helpviewer_keywords:
- CorDebugHandleType enumeration [.NET Framework debugging]
ms.assetid: 84296b55-c2c5-424c-ac9c-8e28e2895945
topic_type:
- apiref
ms.openlocfilehash: 5a957a042875b546a18a17422f355b712756e91c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73098175"
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="b4f32-102">CorDebugHandleType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b4f32-102">CorDebugHandleType Enumeration</span></span>
<span data-ttu-id="b4f32-103">Gibt den Handletyp an.</span><span class="sxs-lookup"><span data-stu-id="b4f32-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4f32-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4f32-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="b4f32-105">Member</span><span class="sxs-lookup"><span data-stu-id="b4f32-105">Members</span></span>  
  
|<span data-ttu-id="b4f32-106">Member</span><span class="sxs-lookup"><span data-stu-id="b4f32-106">Member</span></span>|<span data-ttu-id="b4f32-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4f32-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="b4f32-108">Das Handle ist stark, wodurch verhindert wird, dass ein Objekt von Garbage Collection freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b4f32-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="b4f32-109">Das Handle ist schwach, wodurch verhindert wird, dass ein Objekt von Garbage Collection freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b4f32-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="b4f32-110">Das Handle wird ungültig, wenn das Objekt erfasst wird.</span><span class="sxs-lookup"><span data-stu-id="b4f32-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b4f32-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b4f32-111">Requirements</span></span>  
 <span data-ttu-id="b4f32-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4f32-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4f32-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4f32-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4f32-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4f32-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4f32-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4f32-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4f32-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4f32-116">See also</span></span>

- [<span data-ttu-id="b4f32-117">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="b4f32-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
