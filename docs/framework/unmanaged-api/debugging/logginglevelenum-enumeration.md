---
title: LoggingLevelEnum-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- LoggingLevelEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- LoggingLevelEnum
helpviewer_keywords:
- LoggingLevelEnum enumeration [.NET Framework debugging]
ms.assetid: 09daac08-005a-46b2-beab-408d0820c5e5
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a1f8bb53d53593073df7ef7aa095eeb3b9f8c632
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="logginglevelenum-enumeration"></a><span data-ttu-id="24c92-102">LoggingLevelEnum-Enumeration</span><span class="sxs-lookup"><span data-stu-id="24c92-102">LoggingLevelEnum Enumeration</span></span>
<span data-ttu-id="24c92-103">Gibt den Schweregrad einer beschreibenden Meldung an, die in das Ereignisprotokoll geschrieben wird, wenn ein verwalteter Thread ein Ereignis protokolliert.</span><span class="sxs-lookup"><span data-stu-id="24c92-103">Indicates the severity level of a descriptive message that is written to the event log when a managed thread logs an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24c92-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="24c92-104">Syntax</span></span>  
  
```  
typedef enum LoggingLevelEnum {  
    LTraceLevel0 = 0,  
    LTraceLevel1,  
    LTraceLevel2,  
    LTraceLevel3,  
    LTraceLevel4,  
    LStatusLevel0 = 20,  
    LStatusLevel1,  
    LStatusLevel2,  
    LStatusLevel3,  
    LStatusLevel4,  
    LWarningLevel = 40,  
    LErrorLevel = 50,  
    LPanicLevel = 100  
} LoggingLevelEnum;  
```  
  
## <a name="members"></a><span data-ttu-id="24c92-105">Member</span><span class="sxs-lookup"><span data-stu-id="24c92-105">Members</span></span>  
  
|<span data-ttu-id="24c92-106">Member</span><span class="sxs-lookup"><span data-stu-id="24c92-106">Member</span></span>|<span data-ttu-id="24c92-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="24c92-107">Description</span></span>|  
|------------|-----------------|  
|`LTraceLevel0`|<span data-ttu-id="24c92-108">Die Nachricht ist eine andere Ablaufverfolgungsebene 0.</span><span class="sxs-lookup"><span data-stu-id="24c92-108">The message is a trace level 0.</span></span>|  
|`LTraceLevel1`|<span data-ttu-id="24c92-109">Die Nachricht ist eine andere Ablaufverfolgungsebene 1.</span><span class="sxs-lookup"><span data-stu-id="24c92-109">The message is a trace level 1.</span></span>|  
|`LTraceLevel2`|<span data-ttu-id="24c92-110">Die Nachricht ist eine andere Ablaufverfolgungsebene 2.</span><span class="sxs-lookup"><span data-stu-id="24c92-110">The message is a trace level 2.</span></span>|  
|`LTraceLevel3`|<span data-ttu-id="24c92-111">Die Nachricht ist eine andere Ablaufverfolgungsebene 3.</span><span class="sxs-lookup"><span data-stu-id="24c92-111">The message is a trace level 3.</span></span>|  
|`LTraceLevel4`|<span data-ttu-id="24c92-112">Die Nachricht ist eine andere Ablaufverfolgungsebene 4.</span><span class="sxs-lookup"><span data-stu-id="24c92-112">The message is a trace level 4.</span></span>|  
|`LStatusLevel0`|<span data-ttu-id="24c92-113">Die Nachricht ist, den Status der Ebene 0.</span><span class="sxs-lookup"><span data-stu-id="24c92-113">The message is a status level 0.</span></span>|  
|`LStatusLevel1`|<span data-ttu-id="24c92-114">Die Nachricht ist, den Status der Ebene 1.</span><span class="sxs-lookup"><span data-stu-id="24c92-114">The message is a status level 1.</span></span>|  
|`LStatusLevel2`|<span data-ttu-id="24c92-115">Die Nachricht ist, den Status der Ebene 2.</span><span class="sxs-lookup"><span data-stu-id="24c92-115">The message is a status level 2.</span></span>|  
|`LStatusLevel3`|<span data-ttu-id="24c92-116">Die Nachricht ist, den Status der Ebene 3.</span><span class="sxs-lookup"><span data-stu-id="24c92-116">The message is a status level 3.</span></span>|  
|`LStatusLevel4`|<span data-ttu-id="24c92-117">Die Nachricht ist, den Status der Ebene 4.</span><span class="sxs-lookup"><span data-stu-id="24c92-117">The message is a status level 4.</span></span>|  
|`LWarningLevel`|<span data-ttu-id="24c92-118">Die Meldung ist eine Warnstufe erreicht.</span><span class="sxs-lookup"><span data-stu-id="24c92-118">The message is a warning level.</span></span>|  
|`LErrorLevel`|<span data-ttu-id="24c92-119">Die Meldung ist eine Fehlerstufe erreicht.</span><span class="sxs-lookup"><span data-stu-id="24c92-119">The message is an error level.</span></span>|  
|`LPanicLevel`|<span data-ttu-id="24c92-120">Die Meldung ist ein panic auf.</span><span class="sxs-lookup"><span data-stu-id="24c92-120">The message is a panic level.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24c92-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="24c92-121">Remarks</span></span>  
 <span data-ttu-id="24c92-122">Ruft die common Language Runtime (CLR) die [ICorDebugManagedCallback:: LogMessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md) Methode, um den Debugger zu benachrichtigen, dass ein verwalteter Thread ein Ereignis protokolliert hat.</span><span class="sxs-lookup"><span data-stu-id="24c92-122">The common language runtime (CLR) calls the [ICorDebugManagedCallback::LogMessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md) method to notify the debugger that a managed thread has logged an event.</span></span> <span data-ttu-id="24c92-123">Die CLR übergibt einen Wert, der die `LoggingLevelEnum` Enumeration an, den Schweregrad der Meldung, die der verwaltete Thread in das Ereignisprotokoll geschrieben hat.</span><span class="sxs-lookup"><span data-stu-id="24c92-123">The CLR passes a value of the `LoggingLevelEnum` enumeration to indicate the severity level of the message that the managed thread wrote to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24c92-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="24c92-124">Requirements</span></span>  
 <span data-ttu-id="24c92-125">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24c92-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24c92-126">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="24c92-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="24c92-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24c92-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24c92-128">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24c92-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24c92-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24c92-129">See Also</span></span>  
 <xref:System.Diagnostics.EventLog>  
 [<span data-ttu-id="24c92-130">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="24c92-130">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
