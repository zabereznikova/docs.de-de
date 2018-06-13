---
title: CorDebugCreateProcessFlags-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugCreateProcessFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugCreateProcessFlags
helpviewer_keywords:
- CorDebugCreateProcessFlags enumeration [.NET Framework debugging]
ms.assetid: e709acce-6a17-4346-b38a-467dba567358
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9fdc37676bfae8ac90fde0a7a5b11037b8357e25
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403756"
---
# <a name="cordebugcreateprocessflags-enumeration"></a><span data-ttu-id="3df75-102">CorDebugCreateProcessFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="3df75-102">CorDebugCreateProcessFlags Enumeration</span></span>
<span data-ttu-id="3df75-103">Stellt zusätzliche Debuggingoptionen, die in einem Aufruf verwendet werden, können die [ICorDebug:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="3df75-103">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3df75-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3df75-104">Syntax</span></span>  
  
```  
typedef enum CorDebugCreateProcessFlags {  
    DEBUG_NO_SPECIAL_OPTIONS    = 0x0000  
} CorDebugCreateProcessFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="3df75-105">Member</span><span class="sxs-lookup"><span data-stu-id="3df75-105">Members</span></span>  
  
|<span data-ttu-id="3df75-106">Member</span><span class="sxs-lookup"><span data-stu-id="3df75-106">Member</span></span>|<span data-ttu-id="3df75-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3df75-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_NO_SPECIAL_OPTIONS`|<span data-ttu-id="3df75-108">Ohne besonderen Optionen werden festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3df75-108">No special options are set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3df75-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3df75-109">Requirements</span></span>  
 <span data-ttu-id="3df75-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3df75-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3df75-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3df75-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3df75-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3df75-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3df75-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3df75-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3df75-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3df75-114">See Also</span></span>  
 [<span data-ttu-id="3df75-115">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="3df75-115">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
