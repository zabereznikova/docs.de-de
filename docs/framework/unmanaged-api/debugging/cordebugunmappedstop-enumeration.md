---
title: CorDebugUnmappedStop-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugUnmappedStop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUnmappedStop
helpviewer_keywords:
- CorDebugUnmappedStop enumeration [.NET Framework debugging]
ms.assetid: a684f7d7-d0c2-4690-b721-639e613f11f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c2ea0bf215c0d2abfe9beb29d736f893073d3be8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739513"
---
# <a name="cordebugunmappedstop-enumeration"></a><span data-ttu-id="41080-102">CorDebugUnmappedStop-Enumeration</span><span class="sxs-lookup"><span data-stu-id="41080-102">CorDebugUnmappedStop Enumeration</span></span>
<span data-ttu-id="41080-103">Gibt den Typ von nicht zugeordnetem Code an, der eine Unterbrechung der Codeausführung durch die Schritte auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="41080-103">Specifies the type of unmapped code that can trigger a halt in code execution by the stepper.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41080-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="41080-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugUnmappedStop {  
    STOP_NONE               = 0x0,  
    STOP_PROLOG             = 0x01,  
    STOP_EPILOG             = 0x02,  
    STOP_NO_MAPPING_INFO    = 0x04,  
    STOP_OTHER_UNMAPPED     = 0x08,  
    STOP_UNMANAGED          = 0x10,  
    STOP_ALL                = 0xffff,  
} CorDebugUnmappedStop;  
```  
  
## <a name="members"></a><span data-ttu-id="41080-105">Member</span><span class="sxs-lookup"><span data-stu-id="41080-105">Members</span></span>  
  
|<span data-ttu-id="41080-106">Member</span><span class="sxs-lookup"><span data-stu-id="41080-106">Member</span></span>|<span data-ttu-id="41080-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41080-107">Description</span></span>|  
|------------|-----------------|  
|`STOP_NONE`|<span data-ttu-id="41080-108">Beenden Sie nicht in jeder Art von nicht zugeordnetem Code.</span><span class="sxs-lookup"><span data-stu-id="41080-108">Do not stop in any type of unmapped code.</span></span>|  
|`STOP_PROLOG`|<span data-ttu-id="41080-109">In der Prologcode anhalten.</span><span class="sxs-lookup"><span data-stu-id="41080-109">Stop in prolog code.</span></span>|  
|`STOP_EPILOG`|<span data-ttu-id="41080-110">Beenden Sie im Epilogcode.</span><span class="sxs-lookup"><span data-stu-id="41080-110">Stop in epilog code.</span></span>|  
|`STOP_NO_MAPPING_INFO`|<span data-ttu-id="41080-111">Beenden Sie im Code, der keine Zuordnungsinformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="41080-111">Stop in code that has no mapping information.</span></span>|  
|`STOP_OTHER_UNMAPPED`|<span data-ttu-id="41080-112">Beenden Sie in nicht zugeordnete Code, der nicht in der Prolog, Epilog, ohne-Zuordnungsinformationen oder nicht verwalteten Kategorie passt.</span><span class="sxs-lookup"><span data-stu-id="41080-112">Stop in unmapped code that does not fit into the prolog, epilog, no-mapping-information, or unmanaged category.</span></span>|  
|`STOP_UNMANAGED`|<span data-ttu-id="41080-113">Beenden Sie in nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="41080-113">Stop in unmanaged code.</span></span> <span data-ttu-id="41080-114">Dieser Wert ist nur gültig mit interop-Debuggen.</span><span class="sxs-lookup"><span data-stu-id="41080-114">This value is valid only with interop debugging.</span></span>|  
|`STOP_ALL`|<span data-ttu-id="41080-115">Beenden Sie alle Arten von nicht zugeordnetem Code an.</span><span class="sxs-lookup"><span data-stu-id="41080-115">Stop in all types of unmapped code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41080-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="41080-116">Remarks</span></span>  
 <span data-ttu-id="41080-117">Verwenden der [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) Methode, um die Flags festlegen, die den nicht verwalteten Code angeben, in dem die zugeordnetem wird beendet.</span><span class="sxs-lookup"><span data-stu-id="41080-117">Use the [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) method to set the flags that specify the unmapped code in which the stepper will stop.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41080-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="41080-118">Requirements</span></span>  
 <span data-ttu-id="41080-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41080-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41080-120">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41080-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41080-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41080-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41080-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41080-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41080-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41080-123">See also</span></span>

- [<span data-ttu-id="41080-124">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="41080-124">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
