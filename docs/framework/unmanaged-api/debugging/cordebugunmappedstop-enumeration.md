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
ms.openlocfilehash: 772f1f0dee260ad3752b2f89e5fbe0d6bc27b87b
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795650"
---
# <a name="cordebugunmappedstop-enumeration"></a><span data-ttu-id="e3c56-102">CorDebugUnmappedStop-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e3c56-102">CorDebugUnmappedStop Enumeration</span></span>
<span data-ttu-id="e3c56-103">Gibt den Typ von nicht zugeordnetem Code an, der eine Unterbrechung der Codeausführung durch die Schritte auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="e3c56-103">Specifies the type of unmapped code that can trigger a halt in code execution by the stepper.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3c56-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e3c56-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="e3c56-105">Member</span><span class="sxs-lookup"><span data-stu-id="e3c56-105">Members</span></span>  
  
|<span data-ttu-id="e3c56-106">Member</span><span class="sxs-lookup"><span data-stu-id="e3c56-106">Member</span></span>|<span data-ttu-id="e3c56-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e3c56-107">Description</span></span>|  
|------------|-----------------|  
|`STOP_NONE`|<span data-ttu-id="e3c56-108">Nicht in einem Typ von nicht zugeordnetem Code abbrechen.</span><span class="sxs-lookup"><span data-stu-id="e3c56-108">Do not stop in any type of unmapped code.</span></span>|  
|`STOP_PROLOG`|<span data-ttu-id="e3c56-109">Im Prolog-Code abbrechen.</span><span class="sxs-lookup"><span data-stu-id="e3c56-109">Stop in prolog code.</span></span>|  
|`STOP_EPILOG`|<span data-ttu-id="e3c56-110">Wird im Epilogcode beendet.</span><span class="sxs-lookup"><span data-stu-id="e3c56-110">Stop in epilog code.</span></span>|  
|`STOP_NO_MAPPING_INFO`|<span data-ttu-id="e3c56-111">Wird in Code beendet, der über keine Informationen zur Zuordnung verfügt.</span><span class="sxs-lookup"><span data-stu-id="e3c56-111">Stop in code that has no mapping information.</span></span>|  
|`STOP_OTHER_UNMAPPED`|<span data-ttu-id="e3c56-112">Halten Sie in nicht zugeordnetem Code an, der nicht in die Kategorie Prolog, Epilog, No-Mapping-Information oder nicht verwaltet passt.</span><span class="sxs-lookup"><span data-stu-id="e3c56-112">Stop in unmapped code that does not fit into the prolog, epilog, no-mapping-information, or unmanaged category.</span></span>|  
|`STOP_UNMANAGED`|<span data-ttu-id="e3c56-113">In nicht verwaltetem Code beendet.</span><span class="sxs-lookup"><span data-stu-id="e3c56-113">Stop in unmanaged code.</span></span> <span data-ttu-id="e3c56-114">Dieser Wert ist nur beim Interop-Debuggen gültig.</span><span class="sxs-lookup"><span data-stu-id="e3c56-114">This value is valid only with interop debugging.</span></span>|  
|`STOP_ALL`|<span data-ttu-id="e3c56-115">Wird in allen Typen von nicht zugeordnetem Code beendet.</span><span class="sxs-lookup"><span data-stu-id="e3c56-115">Stop in all types of unmapped code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3c56-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e3c56-116">Remarks</span></span>  
 <span data-ttu-id="e3c56-117">Verwenden Sie die [ICorDebugStepper:: SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) -Methode, um die Flags festzulegen, die den nicht zugeordneten Code angeben, in dem der Stepper angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="e3c56-117">Use the [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) method to set the flags that specify the unmapped code in which the stepper will stop.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3c56-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e3c56-118">Requirements</span></span>  
 <span data-ttu-id="e3c56-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3c56-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3c56-120">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e3c56-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e3c56-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3c56-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3c56-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3c56-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3c56-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e3c56-123">See also</span></span>

- [<span data-ttu-id="e3c56-124">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="e3c56-124">Debugging Enumerations</span></span>](debugging-enumerations.md)
