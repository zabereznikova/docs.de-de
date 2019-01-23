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
ms.openlocfilehash: 0f0f692b692628d50755ce813c66823f940dccb8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54513784"
---
# <a name="cordebugstatechange-enumeration"></a><span data-ttu-id="8577c-102">CorDebugStateChange-Aufzählung</span><span class="sxs-lookup"><span data-stu-id="8577c-102">CorDebugStateChange Enumeration</span></span>
<span data-ttu-id="8577c-103">Beschreibt die Menge der zwischengespeicherten Daten, die auf der Grundlage von Änderungen am Prozess verworfen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="8577c-103">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8577c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8577c-104">Syntax</span></span>  
  
```  
typedef enum CorDebugStateChange  
{  
    PROCESS_RUNNING = 0x0000001,   
    FLUSH_ALL       = 0x0000002,   
} CorDebugStateChange;  
```  
  
## <a name="members"></a><span data-ttu-id="8577c-105">Member</span><span class="sxs-lookup"><span data-stu-id="8577c-105">Members</span></span>  
  
|<span data-ttu-id="8577c-106">Member</span><span class="sxs-lookup"><span data-stu-id="8577c-106">Member</span></span>|<span data-ttu-id="8577c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8577c-107">Description</span></span>|  
|------------|-----------------|  
|`PROCESS_RUNNING`|<span data-ttu-id="8577c-108">Der Prozess hat einen neuen Speicherstatus über die weitere Ausführung erreicht.</span><span class="sxs-lookup"><span data-stu-id="8577c-108">The process reached a new memory state via forward execution.</span></span>|  
|`SET_CONTEXT_FLAG_UNWIND_FRAME`|<span data-ttu-id="8577c-109">Den Prozessspeicher könnte sich in irgendeiner Form vom vorherigen Zustand unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="8577c-109">The process' memory may be arbitrarily different than it was previously.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8577c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8577c-110">Remarks</span></span>  
 <span data-ttu-id="8577c-111">Ein Mitglied der `CorDebugStateChange` Enumeration wird als Argument bereitgestellt, wenn der Debugger Ruft die [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) Methode</span><span class="sxs-lookup"><span data-stu-id="8577c-111">A member of the `CorDebugStateChange` enumeration is provided as an argument when the debugger calls the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) method</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8577c-112">Diese Enumeration ist nur für die Verwendung in .NET Native-Debugszenarios vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="8577c-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8577c-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8577c-113">Requirements</span></span>  
 <span data-ttu-id="8577c-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8577c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8577c-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8577c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8577c-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8577c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8577c-117">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8577c-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8577c-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8577c-118">See also</span></span>
- [<span data-ttu-id="8577c-119">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="8577c-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="8577c-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="8577c-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
