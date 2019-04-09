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
ms.openlocfilehash: c1cea8adcd12ecb3078e4469e6b018ed49064e0b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175928"
---
# <a name="cordebugunmappedstop-enumeration"></a><span data-ttu-id="8bafb-102">CorDebugUnmappedStop-Enumeration</span><span class="sxs-lookup"><span data-stu-id="8bafb-102">CorDebugUnmappedStop Enumeration</span></span>
<span data-ttu-id="8bafb-103">Gibt den Typ von nicht zugeordnetem Code an, der eine Unterbrechung der Codeausführung durch die Schritte auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="8bafb-103">Specifies the type of unmapped code that can trigger a halt in code execution by the stepper.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bafb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8bafb-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="8bafb-105">Member</span><span class="sxs-lookup"><span data-stu-id="8bafb-105">Members</span></span>  
  
|<span data-ttu-id="8bafb-106">Member</span><span class="sxs-lookup"><span data-stu-id="8bafb-106">Member</span></span>|<span data-ttu-id="8bafb-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8bafb-107">Description</span></span>|  
|------------|-----------------|  
|`STOP_NONE`|<span data-ttu-id="8bafb-108">Beenden Sie nicht in jeder Art von nicht zugeordnetem Code.</span><span class="sxs-lookup"><span data-stu-id="8bafb-108">Do not stop in any type of unmapped code.</span></span>|  
|`STOP_PROLOG`|<span data-ttu-id="8bafb-109">In der Prologcode anhalten.</span><span class="sxs-lookup"><span data-stu-id="8bafb-109">Stop in prolog code.</span></span>|  
|`STOP_EPILOG`|<span data-ttu-id="8bafb-110">Beenden Sie im Epilogcode.</span><span class="sxs-lookup"><span data-stu-id="8bafb-110">Stop in epilog code.</span></span>|  
|`STOP_NO_MAPPING_INFO`|<span data-ttu-id="8bafb-111">Beenden Sie im Code, der keine Zuordnungsinformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="8bafb-111">Stop in code that has no mapping information.</span></span>|  
|`STOP_OTHER_UNMAPPED`|<span data-ttu-id="8bafb-112">Beenden Sie in nicht zugeordnete Code, der nicht in der Prolog, Epilog, ohne-Zuordnungsinformationen oder nicht verwalteten Kategorie passt.</span><span class="sxs-lookup"><span data-stu-id="8bafb-112">Stop in unmapped code that does not fit into the prolog, epilog, no-mapping-information, or unmanaged category.</span></span>|  
|`STOP_UNMANAGED`|<span data-ttu-id="8bafb-113">Beenden Sie in nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="8bafb-113">Stop in unmanaged code.</span></span> <span data-ttu-id="8bafb-114">Dieser Wert ist nur gültig mit interop-Debuggen.</span><span class="sxs-lookup"><span data-stu-id="8bafb-114">This value is valid only with interop debugging.</span></span>|  
|`STOP_ALL`|<span data-ttu-id="8bafb-115">Beenden Sie alle Arten von nicht zugeordnetem Code an.</span><span class="sxs-lookup"><span data-stu-id="8bafb-115">Stop in all types of unmapped code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8bafb-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8bafb-116">Remarks</span></span>  
 <span data-ttu-id="8bafb-117">Verwenden der [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) Methode, um die Flags festlegen, die den nicht verwalteten Code angeben, in dem die zugeordnetem wird beendet.</span><span class="sxs-lookup"><span data-stu-id="8bafb-117">Use the [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) method to set the flags that specify the unmapped code in which the stepper will stop.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bafb-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8bafb-118">Requirements</span></span>  
 <span data-ttu-id="8bafb-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8bafb-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bafb-120">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8bafb-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8bafb-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8bafb-121">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="8bafb-122">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="8bafb-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8bafb-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8bafb-123">See also</span></span>

- [<span data-ttu-id="8bafb-124">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="8bafb-124">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
