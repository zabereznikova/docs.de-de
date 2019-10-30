---
title: LogSwitchCallReason-Enumeration
ms.date: 03/30/2017
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
ms.openlocfilehash: 2a6ca9f4d74c508ac0a2af68c2a5b0a3e6d6b217
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139183"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="7f0bc-102">LogSwitchCallReason-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7f0bc-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="7f0bc-103">Gibt den Vorgang an, der für einen Debug-/Ablaufverfolgungsschalter ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="7f0bc-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f0bc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7f0bc-104">Syntax</span></span>  
  
```cpp  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="7f0bc-105">Member</span><span class="sxs-lookup"><span data-stu-id="7f0bc-105">Members</span></span>  
  
|<span data-ttu-id="7f0bc-106">Member</span><span class="sxs-lookup"><span data-stu-id="7f0bc-106">Member</span></span>|<span data-ttu-id="7f0bc-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7f0bc-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="7f0bc-108">Ein Debugger/Ablauf Verfolgungs Schalter wurde erstellt.</span><span class="sxs-lookup"><span data-stu-id="7f0bc-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="7f0bc-109">Ein Debugger/Ablauf Verfolgungs Schalter wurde geändert.</span><span class="sxs-lookup"><span data-stu-id="7f0bc-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="7f0bc-110">Ein Debugger/Ablauf Verfolgungs Schalter wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="7f0bc-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7f0bc-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7f0bc-111">Requirements</span></span>  
 <span data-ttu-id="7f0bc-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f0bc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f0bc-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7f0bc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7f0bc-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f0bc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f0bc-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f0bc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f0bc-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f0bc-116">See also</span></span>

- [<span data-ttu-id="7f0bc-117">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="7f0bc-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
