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
ms.openlocfilehash: 15572037940f7c45ec5dcb7e34599756e15fd3bd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793910"
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="8d4ca-102">CorDebugHandleType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="8d4ca-102">CorDebugHandleType Enumeration</span></span>
<span data-ttu-id="8d4ca-103">Gibt den Handletyp an.</span><span class="sxs-lookup"><span data-stu-id="8d4ca-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d4ca-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8d4ca-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="8d4ca-105">Member</span><span class="sxs-lookup"><span data-stu-id="8d4ca-105">Members</span></span>  
  
|<span data-ttu-id="8d4ca-106">Member</span><span class="sxs-lookup"><span data-stu-id="8d4ca-106">Member</span></span>|<span data-ttu-id="8d4ca-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8d4ca-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="8d4ca-108">Das Handle ist stark, wodurch verhindert wird, dass ein Objekt von Garbage Collection freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8d4ca-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="8d4ca-109">Das Handle ist schwach, wodurch verhindert wird, dass ein Objekt von Garbage Collection freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8d4ca-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="8d4ca-110">Das Handle wird ungültig, wenn das Objekt erfasst wird.</span><span class="sxs-lookup"><span data-stu-id="8d4ca-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8d4ca-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8d4ca-111">Requirements</span></span>  
 <span data-ttu-id="8d4ca-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d4ca-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d4ca-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d4ca-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d4ca-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d4ca-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d4ca-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d4ca-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d4ca-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8d4ca-116">See also</span></span>

- [<span data-ttu-id="8d4ca-117">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="8d4ca-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
