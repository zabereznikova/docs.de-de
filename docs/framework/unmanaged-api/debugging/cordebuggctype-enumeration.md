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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182922"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="4f748-102">CorDebugGCType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="4f748-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="4f748-103">Gibt an, ob die Garbage Collection auf einer Arbeitsstation oder einen Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4f748-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f748-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4f748-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f748-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4f748-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="4f748-106">Member</span><span class="sxs-lookup"><span data-stu-id="4f748-106">Members</span></span>  
  
|<span data-ttu-id="4f748-107">Membername</span><span class="sxs-lookup"><span data-stu-id="4f748-107">Member name</span></span>|<span data-ttu-id="4f748-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4f748-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="4f748-109">Der Garbage Collector wird auf einer Arbeitsstation ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4f748-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="4f748-110">Der Garbage Collector wird auf einem Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4f748-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f748-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4f748-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f748-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4f748-112">Requirements</span></span>  
 <span data-ttu-id="4f748-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f748-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f748-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f748-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f748-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f748-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="4f748-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="4f748-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4f748-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f748-117">See also</span></span>

- [<span data-ttu-id="4f748-118">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="4f748-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
