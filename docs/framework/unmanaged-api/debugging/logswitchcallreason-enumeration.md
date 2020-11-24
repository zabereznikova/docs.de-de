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
ms.openlocfilehash: dfb34595530a47b74762610f5824b68ea00a8a69
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671940"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="36f92-102">LogSwitchCallReason-Enumeration</span><span class="sxs-lookup"><span data-stu-id="36f92-102">LogSwitchCallReason Enumeration</span></span>

<span data-ttu-id="36f92-103">Gibt den Vorgang an, der für einen Debug-/Ablaufverfolgungsschalter ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="36f92-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36f92-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="36f92-104">Syntax</span></span>  
  
```cpp  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="36f92-105">Member</span><span class="sxs-lookup"><span data-stu-id="36f92-105">Members</span></span>  
  
|<span data-ttu-id="36f92-106">Member</span><span class="sxs-lookup"><span data-stu-id="36f92-106">Member</span></span>|<span data-ttu-id="36f92-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="36f92-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="36f92-108">Ein Debugger/Ablauf Verfolgungs Schalter wurde erstellt.</span><span class="sxs-lookup"><span data-stu-id="36f92-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="36f92-109">Ein Debugger/Ablauf Verfolgungs Schalter wurde geändert.</span><span class="sxs-lookup"><span data-stu-id="36f92-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="36f92-110">Ein Debugger/Ablauf Verfolgungs Schalter wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="36f92-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="36f92-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="36f92-111">Requirements</span></span>  

 <span data-ttu-id="36f92-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36f92-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36f92-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="36f92-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="36f92-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36f92-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36f92-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36f92-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36f92-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="36f92-116">See also</span></span>

- [<span data-ttu-id="36f92-117">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="36f92-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
