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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f6f5cd47abd4c17021bc324898a096ff70a3db2e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739995"
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="726b1-102">CorDebugHandleType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="726b1-102">CorDebugHandleType Enumeration</span></span>
<span data-ttu-id="726b1-103">Gibt den Handletyp an.</span><span class="sxs-lookup"><span data-stu-id="726b1-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="726b1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="726b1-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="726b1-105">Member</span><span class="sxs-lookup"><span data-stu-id="726b1-105">Members</span></span>  
  
|<span data-ttu-id="726b1-106">Member</span><span class="sxs-lookup"><span data-stu-id="726b1-106">Member</span></span>|<span data-ttu-id="726b1-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="726b1-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="726b1-108">Das Handle ist stark, dadurch wird verhindert, dass ein Objekt durch die Garbagecollection freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="726b1-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="726b1-109">Das Handle ist schwach ist, die ein Objekt verhindert nicht, dass durch die Garbagecollection freigegeben.</span><span class="sxs-lookup"><span data-stu-id="726b1-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="726b1-110">Das Handle wird ungültig, wenn das Objekt gesammelt werden.</span><span class="sxs-lookup"><span data-stu-id="726b1-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="726b1-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="726b1-111">Requirements</span></span>  
 <span data-ttu-id="726b1-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="726b1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="726b1-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="726b1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="726b1-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="726b1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="726b1-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="726b1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="726b1-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="726b1-116">See also</span></span>

- [<span data-ttu-id="726b1-117">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="726b1-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
