---
title: CorDebugStateChange-Aufzählung
ms.date: 03/30/2017
api_name:
- CorDebugStateChange
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1d4424ab-5143-4e50-a84a-ceeb4ddf3bba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 841108457293e3377ee87f9c7d7c6898340e51b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404345"
---
# <a name="cordebugstatechange-enumeration"></a><span data-ttu-id="70619-102">CorDebugStateChange-Aufzählung</span><span class="sxs-lookup"><span data-stu-id="70619-102">CorDebugStateChange Enumeration</span></span>
<span data-ttu-id="70619-103">Beschreibt die Menge der zwischengespeicherten Daten, die auf der Grundlage von Änderungen am Prozess verworfen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="70619-103">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70619-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="70619-104">Syntax</span></span>  
  
```  
typedef enum CorDebugStateChange  
{  
    PROCESS_RUNNING = 0x0000001,   
    FLUSH_ALL       = 0x0000002,   
} CorDebugStateChange;  
```  
  
## <a name="members"></a><span data-ttu-id="70619-105">Member</span><span class="sxs-lookup"><span data-stu-id="70619-105">Members</span></span>  
  
|<span data-ttu-id="70619-106">Member</span><span class="sxs-lookup"><span data-stu-id="70619-106">Member</span></span>|<span data-ttu-id="70619-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="70619-107">Description</span></span>|  
|------------|-----------------|  
|`PROCESS_RUNNING`|<span data-ttu-id="70619-108">Der Prozess hat einen neuen Speicherstatus über die weitere Ausführung erreicht.</span><span class="sxs-lookup"><span data-stu-id="70619-108">The process reached a new memory state via forward execution.</span></span>|  
|`SET_CONTEXT_FLAG_UNWIND_FRAME`|<span data-ttu-id="70619-109">Den Prozessspeicher könnte sich in irgendeiner Form vom vorherigen Zustand unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="70619-109">The process' memory may be arbitrarily different than it was previously.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70619-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="70619-110">Remarks</span></span>  
 <span data-ttu-id="70619-111">Ein Mitglied der `CorDebugStateChange` Enumeration wird als Argument bereitgestellt, wenn der Debugger Ruft die [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) Methode</span><span class="sxs-lookup"><span data-stu-id="70619-111">A member of the `CorDebugStateChange` enumeration is provided as an argument when the debugger calls the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) method</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70619-112">Diese Enumeration ist nur für die Verwendung in .NET Native-Debugszenarios vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="70619-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70619-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="70619-113">Requirements</span></span>  
 <span data-ttu-id="70619-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70619-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70619-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="70619-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="70619-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70619-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70619-117">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70619-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70619-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70619-118">See Also</span></span>  
 [<span data-ttu-id="70619-119">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="70619-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="70619-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="70619-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
