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
ms.openlocfilehash: 29781666c106755f96f945325e3a8953bf93b211
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790349"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="b7a31-102">LogSwitchCallReason-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b7a31-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="b7a31-103">Gibt den Vorgang an, der für einen Debug-/Ablaufverfolgungsschalter ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="b7a31-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7a31-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b7a31-104">Syntax</span></span>  
  
```cpp  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="b7a31-105">Member</span><span class="sxs-lookup"><span data-stu-id="b7a31-105">Members</span></span>  
  
|<span data-ttu-id="b7a31-106">Member</span><span class="sxs-lookup"><span data-stu-id="b7a31-106">Member</span></span>|<span data-ttu-id="b7a31-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b7a31-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="b7a31-108">Ein Debugger/Ablauf Verfolgungs Schalter wurde erstellt.</span><span class="sxs-lookup"><span data-stu-id="b7a31-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="b7a31-109">Ein Debugger/Ablauf Verfolgungs Schalter wurde geändert.</span><span class="sxs-lookup"><span data-stu-id="b7a31-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="b7a31-110">Ein Debugger/Ablauf Verfolgungs Schalter wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b7a31-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b7a31-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b7a31-111">Requirements</span></span>  
 <span data-ttu-id="b7a31-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7a31-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7a31-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7a31-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7a31-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7a31-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7a31-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7a31-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7a31-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7a31-116">See also</span></span>

- [<span data-ttu-id="b7a31-117">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="b7a31-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
