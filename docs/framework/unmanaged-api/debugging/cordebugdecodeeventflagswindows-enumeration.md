---
title: "CorDebugDecodeEventFlagsWindows-Aufzählung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugDecodeEventFlagsWindows
api_location: mscordbi.dll
api_type: COM
ms.assetid: aa6cf962-30ae-4cfd-8895-826deeb46a54
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: facde76ec24d90795de7dfb70bfe5772a6f21531
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a><span data-ttu-id="d3982-102">CorDebugDecodeEventFlagsWindows-Aufzählung</span><span class="sxs-lookup"><span data-stu-id="d3982-102">CorDebugDecodeEventFlagsWindows Enumeration</span></span>
<span data-ttu-id="d3982-103">Weitere Informationen zu Debug-Ereignissen auf der Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="d3982-103">Provides additional information about debug events on the Windows platform.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3982-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d3982-104">Syntax</span></span>  
  
```  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a><span data-ttu-id="d3982-105">Member</span><span class="sxs-lookup"><span data-stu-id="d3982-105">Members</span></span>  
  
|<span data-ttu-id="d3982-106">Member</span><span class="sxs-lookup"><span data-stu-id="d3982-106">Member</span></span>|<span data-ttu-id="d3982-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d3982-107">Description</span></span>|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|<span data-ttu-id="d3982-108">Gibt an, dass das Debug-Ereignis eine Ausnahme der ersten Chance ist.</span><span class="sxs-lookup"><span data-stu-id="d3982-108">Indicates that the debug event is a first-chance exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3982-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d3982-109">Remarks</span></span>  
 <span data-ttu-id="d3982-110">Die [icordebugprocess6:: Decodeevent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) Methode enthält einen `dwFlags` Parameter, der zusätzliche Informationen über ein Debug-Ereignis bereitstellt und dessen Wert ist abhängig von der Zielarchitektur.</span><span class="sxs-lookup"><span data-stu-id="d3982-110">The [ICorDebugProcess6::DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method includes a `dwFlags` parameter that provides additional information about a debug event and whose value is dependent on the target architecture.</span></span> <span data-ttu-id="d3982-111">Die `CorDebugDecodeEventFlagsWindows` -Enumeration kann mit Debug-Ereignissen auf der Windows-Plattform verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d3982-111">The `CorDebugDecodeEventFlagsWindows` enumeration can be used with debug events on the Windows platform.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3982-112">Diese Enumeration ist nur für die Verwendung in .NET Native-Debugszenarios vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="d3982-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3982-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d3982-113">Requirements</span></span>  
 <span data-ttu-id="d3982-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3982-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3982-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d3982-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d3982-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3982-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3982-117">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3982-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3982-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3982-118">See Also</span></span>  
 [<span data-ttu-id="d3982-119">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="d3982-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
