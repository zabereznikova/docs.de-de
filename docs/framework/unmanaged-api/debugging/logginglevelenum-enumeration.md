---
title: LoggingLevelEnum-Enumeration
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2fe8e1355382273a681e927897f4a8ff5814b8de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59086506"
---
# <a name="logginglevelenum-enumeration"></a><span data-ttu-id="d33e5-102">LoggingLevelEnum-Enumeration</span><span class="sxs-lookup"><span data-stu-id="d33e5-102">LoggingLevelEnum Enumeration</span></span>
<span data-ttu-id="d33e5-103">Gibt den Schweregrad einer beschreibenden Meldung an, die in das Ereignisprotokoll geschrieben wird, wenn ein verwalteter Thread ein Ereignis protokolliert.</span><span class="sxs-lookup"><span data-stu-id="d33e5-103">Indicates the severity level of a descriptive message that is written to the event log when a managed thread logs an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d33e5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d33e5-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="d33e5-105">Member</span><span class="sxs-lookup"><span data-stu-id="d33e5-105">Members</span></span>  
  
|<span data-ttu-id="d33e5-106">Member</span><span class="sxs-lookup"><span data-stu-id="d33e5-106">Member</span></span>|<span data-ttu-id="d33e5-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d33e5-107">Description</span></span>|  
|------------|-----------------|  
|`LTraceLevel0`|<span data-ttu-id="d33e5-108">Die Meldung ist ein Trace-Ebene-0.</span><span class="sxs-lookup"><span data-stu-id="d33e5-108">The message is a trace level 0.</span></span>|  
|`LTraceLevel1`|<span data-ttu-id="d33e5-109">Die Meldung ist ein Trace-Ebene-1.</span><span class="sxs-lookup"><span data-stu-id="d33e5-109">The message is a trace level 1.</span></span>|  
|`LTraceLevel2`|<span data-ttu-id="d33e5-110">Die Meldung ist ein Trace-Ebene-2.</span><span class="sxs-lookup"><span data-stu-id="d33e5-110">The message is a trace level 2.</span></span>|  
|`LTraceLevel3`|<span data-ttu-id="d33e5-111">Die Meldung ist ein 3-Ablaufverfolgungsebene.</span><span class="sxs-lookup"><span data-stu-id="d33e5-111">The message is a trace level 3.</span></span>|  
|`LTraceLevel4`|<span data-ttu-id="d33e5-112">Die Meldung ist ein 4-Ablaufverfolgungsebene.</span><span class="sxs-lookup"><span data-stu-id="d33e5-112">The message is a trace level 4.</span></span>|  
|`LStatusLevel0`|<span data-ttu-id="d33e5-113">Die Nachricht ist, den Status der Ebene 0.</span><span class="sxs-lookup"><span data-stu-id="d33e5-113">The message is a status level 0.</span></span>|  
|`LStatusLevel1`|<span data-ttu-id="d33e5-114">Die Nachricht ist, den Status der Ebene 1.</span><span class="sxs-lookup"><span data-stu-id="d33e5-114">The message is a status level 1.</span></span>|  
|`LStatusLevel2`|<span data-ttu-id="d33e5-115">Die Nachricht ist, den Status der Ebene 2.</span><span class="sxs-lookup"><span data-stu-id="d33e5-115">The message is a status level 2.</span></span>|  
|`LStatusLevel3`|<span data-ttu-id="d33e5-116">Die Nachricht ist, den Status der Ebene 3.</span><span class="sxs-lookup"><span data-stu-id="d33e5-116">The message is a status level 3.</span></span>|  
|`LStatusLevel4`|<span data-ttu-id="d33e5-117">Die Nachricht ist, den Status der Ebene 4.</span><span class="sxs-lookup"><span data-stu-id="d33e5-117">The message is a status level 4.</span></span>|  
|`LWarningLevel`|<span data-ttu-id="d33e5-118">Die Meldung ist eine Warnstufe erreicht.</span><span class="sxs-lookup"><span data-stu-id="d33e5-118">The message is a warning level.</span></span>|  
|`LErrorLevel`|<span data-ttu-id="d33e5-119">Die Meldung ist ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="d33e5-119">The message is an error level.</span></span>|  
|`LPanicLevel`|<span data-ttu-id="d33e5-120">Die Meldung ist eine panic Ebene.</span><span class="sxs-lookup"><span data-stu-id="d33e5-120">The message is a panic level.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d33e5-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d33e5-121">Remarks</span></span>  
 <span data-ttu-id="d33e5-122">Ruft die common Language Runtime (CLR) die [ICorDebugManagedCallback:: LogMessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md) Methode, um den Debugger zu benachrichtigen, dass ein verwalteter Thread ein Ereignis protokolliert hat.</span><span class="sxs-lookup"><span data-stu-id="d33e5-122">The common language runtime (CLR) calls the [ICorDebugManagedCallback::LogMessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md) method to notify the debugger that a managed thread has logged an event.</span></span> <span data-ttu-id="d33e5-123">Die CLR übergibt den Wert der `LoggingLevelEnum` Enumeration an, dass der Schweregrad der Meldung, die der verwaltete Thread in das Ereignisprotokoll geschrieben.</span><span class="sxs-lookup"><span data-stu-id="d33e5-123">The CLR passes a value of the `LoggingLevelEnum` enumeration to indicate the severity level of the message that the managed thread wrote to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d33e5-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d33e5-124">Requirements</span></span>  
 <span data-ttu-id="d33e5-125">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d33e5-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d33e5-126">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d33e5-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d33e5-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d33e5-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d33e5-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d33e5-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d33e5-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d33e5-129">See also</span></span>

- <xref:System.Diagnostics.EventLog>
- [<span data-ttu-id="d33e5-130">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="d33e5-130">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
