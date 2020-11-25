---
title: CorDebugDecodeEventFlagsWindows-Aufzählung
ms.date: 03/30/2017
api_name:
- CorDebugDecodeEventFlagsWindows
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aa6cf962-30ae-4cfd-8895-826deeb46a54
topic_type:
- apiref
ms.openlocfilehash: 60eab923aac5dea927105e8ca9fa77eb5708f5ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733359"
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a><span data-ttu-id="677dc-102">CorDebugDecodeEventFlagsWindows-Aufzählung</span><span class="sxs-lookup"><span data-stu-id="677dc-102">CorDebugDecodeEventFlagsWindows Enumeration</span></span>

<span data-ttu-id="677dc-103">Weitere Informationen zu Debug-Ereignissen auf der Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="677dc-103">Provides additional information about debug events on the Windows platform.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="677dc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="677dc-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a><span data-ttu-id="677dc-105">Member</span><span class="sxs-lookup"><span data-stu-id="677dc-105">Members</span></span>  
  
|<span data-ttu-id="677dc-106">Member</span><span class="sxs-lookup"><span data-stu-id="677dc-106">Member</span></span>|<span data-ttu-id="677dc-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="677dc-107">Description</span></span>|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|<span data-ttu-id="677dc-108">Gibt an, dass das Debug-Ereignis eine Ausnahme der ersten Chance ist.</span><span class="sxs-lookup"><span data-stu-id="677dc-108">Indicates that the debug event is a first-chance exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="677dc-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="677dc-109">Remarks</span></span>  

 <span data-ttu-id="677dc-110">Die [ICorDebugProcess6::D ecodeevent](icordebugprocess6-decodeevent-method.md) -Methode enthält einen `dwFlags` Parameter, der zusätzliche Informationen zu einem Debugereignis bereitstellt und dessen Wert von der Zielarchitektur abhängt.</span><span class="sxs-lookup"><span data-stu-id="677dc-110">The [ICorDebugProcess6::DecodeEvent](icordebugprocess6-decodeevent-method.md) method includes a `dwFlags` parameter that provides additional information about a debug event and whose value is dependent on the target architecture.</span></span> <span data-ttu-id="677dc-111">Die `CorDebugDecodeEventFlagsWindows` -Enumeration kann mit Debug-Ereignissen auf der Windows-Plattform verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="677dc-111">The `CorDebugDecodeEventFlagsWindows` enumeration can be used with debug events on the Windows platform.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="677dc-112">Diese Enumeration ist nur für die Verwendung in .NET Native-Debugszenarien vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="677dc-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="677dc-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="677dc-113">Requirements</span></span>  

 <span data-ttu-id="677dc-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="677dc-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="677dc-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="677dc-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="677dc-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="677dc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="677dc-117">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="677dc-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="677dc-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="677dc-118">See also</span></span>

- [<span data-ttu-id="677dc-119">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="677dc-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
