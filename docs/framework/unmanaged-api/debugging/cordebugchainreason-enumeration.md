---
title: CorDebugChainReason-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugChainReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugChainReason
helpviewer_keywords:
- CorDebugChainReason enumeration [.NET Framework debugging]
ms.assetid: c915da51-50b2-41df-841a-2b971f4d0975
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cac790ebbf25ee3095db293ba90612be37fff9b9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190443"
---
# <a name="cordebugchainreason-enumeration"></a><span data-ttu-id="e4a02-102">CorDebugChainReason-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e4a02-102">CorDebugChainReason Enumeration</span></span>
<span data-ttu-id="e4a02-103">Gibt den Grund oder die Gründe für die Initiierung einer Aufrufkette an.</span><span class="sxs-lookup"><span data-stu-id="e4a02-103">Indicates the reason or reasons for the initiation of a call chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4a02-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4a02-104">Syntax</span></span>  
  
```  
typedef enum CorDebugChainReason {  
    CHAIN_NONE              = 0x000,  
    CHAIN_CLASS_INIT        = 0x001,  
    CHAIN_EXCEPTION_FILTER  = 0x002,  
    CHAIN_SECURITY          = 0x004,  
    CHAIN_CONTEXT_POLICY    = 0x008,  
    CHAIN_INTERCEPTION      = 0x010,  
    CHAIN_PROCESS_START     = 0x020,  
    CHAIN_THREAD_START      = 0x040,  
    CHAIN_ENTER_MANAGED     = 0x080,  
    CHAIN_ENTER_UNMANAGED   = 0x100,  
    CHAIN_DEBUGGER_EVAL     = 0x200,  
    CHAIN_CONTEXT_SWITCH    = 0x400,  
    CHAIN_FUNC_EVAL         = 0x800  
} CorDebugChainReason;  
```  
  
## <a name="members"></a><span data-ttu-id="e4a02-105">Member</span><span class="sxs-lookup"><span data-stu-id="e4a02-105">Members</span></span>  
  
|<span data-ttu-id="e4a02-106">Member</span><span class="sxs-lookup"><span data-stu-id="e4a02-106">Member</span></span>|<span data-ttu-id="e4a02-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e4a02-107">Description</span></span>|  
|------------|-----------------|  
|`CHAIN_NONE`|<span data-ttu-id="e4a02-108">Es wurde keine Aufrufkette initiiert.</span><span class="sxs-lookup"><span data-stu-id="e4a02-108">No call chain has been initiated.</span></span>|  
|`CHAIN_CLASS_INIT`|<span data-ttu-id="e4a02-109">Die Kette wurde durch einen Konstruktor initiiert.</span><span class="sxs-lookup"><span data-stu-id="e4a02-109">The chain was initiated by a constructor.</span></span>|  
|`CHAIN_EXCEPTION_FILTER`|<span data-ttu-id="e4a02-110">Die Kette wurde durch einen Ausnahmefilter initiiert.</span><span class="sxs-lookup"><span data-stu-id="e4a02-110">The chain was initiated by an exception filter.</span></span>|  
|`CHAIN_SECURITY`|<span data-ttu-id="e4a02-111">Die Kette wurde durch Code initiiert, der Sicherheit erzwingt.</span><span class="sxs-lookup"><span data-stu-id="e4a02-111">The chain was initiated by code that enforces security.</span></span>|  
|`CHAIN_CONTEXT_POLICY`|<span data-ttu-id="e4a02-112">Die Kette wurde durch eine Kontextrichtlinie initiiert.</span><span class="sxs-lookup"><span data-stu-id="e4a02-112">The chain was initiated by a context policy.</span></span>|  
|`CHAIN_INTERCEPTION`|<span data-ttu-id="e4a02-113">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="e4a02-113">Not used.</span></span>|  
|`CHAIN_PROCESS_START`|<span data-ttu-id="e4a02-114">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="e4a02-114">Not used.</span></span>|  
|`CHAIN_THREAD_START`|<span data-ttu-id="e4a02-115">Die Kette wurde durch den Start einer Threadausführung initiiert.</span><span class="sxs-lookup"><span data-stu-id="e4a02-115">The chain was initiated by the start of a thread execution.</span></span>|  
|`CHAIN_ENTER_MANAGED`|<span data-ttu-id="e4a02-116">Die Kette wurde durch den Einstieg in verwalteten Code initiiert.</span><span class="sxs-lookup"><span data-stu-id="e4a02-116">The chain was initiated by entry into managed code.</span></span>|  
|`CHAIN_ENTER_UNMANAGED`|<span data-ttu-id="e4a02-117">Die Kette wurde durch den Einstieg in nicht verwalteten Code initiiert.</span><span class="sxs-lookup"><span data-stu-id="e4a02-117">The chain was initiated by entry into unmanaged code.</span></span>|  
|`CHAIN_DEBUGGER_EVAL`|<span data-ttu-id="e4a02-118">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="e4a02-118">Not used.</span></span>|  
|`CHAIN_CONTEXT_SWITCH`|<span data-ttu-id="e4a02-119">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="e4a02-119">Not used.</span></span>|  
|`CHAIN_FUNC_EVAL`|<span data-ttu-id="e4a02-120">Die Kette wurde durch eine Funktionsauswertung initiiert.</span><span class="sxs-lookup"><span data-stu-id="e4a02-120">The chain was initiated by a function evaluation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4a02-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e4a02-121">Remarks</span></span>  
 <span data-ttu-id="e4a02-122">Verwenden der [ICorDebugChain:: GetReason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md) Methode, um die Gründe für die Initiierung einer Aufrufkette zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="e4a02-122">Use the [ICorDebugChain::GetReason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md) method to ascertain the reasons for the initiation of a call chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4a02-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e4a02-123">Requirements</span></span>  
 <span data-ttu-id="e4a02-124">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4a02-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4a02-125">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4a02-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4a02-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4a02-126">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e4a02-127">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="e4a02-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e4a02-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4a02-128">See also</span></span>

- [<span data-ttu-id="e4a02-129">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="e4a02-129">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
