---
title: CorDebugHandleType-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugHandleType
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugHandleType
helpviewer_keywords: CorDebugHandleType enumeration [.NET Framework debugging]
ms.assetid: 84296b55-c2c5-424c-ac9c-8e28e2895945
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ef0b892d8dc277286114e8f9eda8d0f16833e1d8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="24c4e-102">CorDebugHandleType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="24c4e-102">CorDebugHandleType Enumeration</span></span>
<span data-ttu-id="24c4e-103">Gibt den Handletyp an.</span><span class="sxs-lookup"><span data-stu-id="24c4e-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24c4e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="24c4e-104">Syntax</span></span>  
  
```  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="24c4e-105">Member</span><span class="sxs-lookup"><span data-stu-id="24c4e-105">Members</span></span>  
  
|<span data-ttu-id="24c4e-106">Member</span><span class="sxs-lookup"><span data-stu-id="24c4e-106">Member</span></span>|<span data-ttu-id="24c4e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="24c4e-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="24c4e-108">Das Handle ist stark, dadurch wird verhindert, dass ein Objekt, das von der Garbagecollection zurückgefordert wird.</span><span class="sxs-lookup"><span data-stu-id="24c4e-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="24c4e-109">Das Handle ist schwach, die ein Objekt verhindert nicht, die von der Garbagecollection zurückgefordert wird.</span><span class="sxs-lookup"><span data-stu-id="24c4e-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="24c4e-110">Das Handle wird ungültig, wenn das Objekt gesammelt werden.</span><span class="sxs-lookup"><span data-stu-id="24c4e-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="24c4e-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="24c4e-111">Requirements</span></span>  
 <span data-ttu-id="24c4e-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24c4e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24c4e-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="24c4e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="24c4e-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24c4e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24c4e-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24c4e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24c4e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24c4e-116">See Also</span></span>  
 [<span data-ttu-id="24c4e-117">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="24c4e-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
