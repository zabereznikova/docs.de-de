---
title: LogSwitchCallReason-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- LogSwitchCallReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- LogSwitchCallReason
helpviewer_keywords:
- LogSwitchCallReason enumeration [.NET Framework debugging]
ms.assetid: 5bbb8d1b-bbc4-47b0-b1b1-2d54cc0be291
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3dcd91001dfd823416b08ba49ba4ed12a2c4d058
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="c1426-102">LogSwitchCallReason-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c1426-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="c1426-103">Gibt den Vorgang an, der für einen Debug-/Ablaufverfolgungsschalter ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="c1426-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1426-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1426-104">Syntax</span></span>  
  
```  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="c1426-105">Member</span><span class="sxs-lookup"><span data-stu-id="c1426-105">Members</span></span>  
  
|<span data-ttu-id="c1426-106">Member</span><span class="sxs-lookup"><span data-stu-id="c1426-106">Member</span></span>|<span data-ttu-id="c1426-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1426-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="c1426-108">Ein Debug-/Ablaufverfolgungsschalter wurde erstellt.</span><span class="sxs-lookup"><span data-stu-id="c1426-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="c1426-109">Ein Debug-/Ablaufverfolgungsschalter wurde geändert.</span><span class="sxs-lookup"><span data-stu-id="c1426-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="c1426-110">Ein Debug-/Ablaufverfolgungsschalter wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="c1426-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c1426-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c1426-111">Requirements</span></span>  
 <span data-ttu-id="c1426-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1426-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1426-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c1426-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c1426-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1426-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1426-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1426-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1426-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1426-116">See Also</span></span>  
 [<span data-ttu-id="c1426-117">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="c1426-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
