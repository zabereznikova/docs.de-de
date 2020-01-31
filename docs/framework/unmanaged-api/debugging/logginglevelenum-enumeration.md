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
ms.openlocfilehash: 1677798abdb8994d34c82a71e97a2c858209c18e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790391"
---
# <a name="logginglevelenum-enumeration"></a><span data-ttu-id="6a0b1-102">LoggingLevelEnum-Enumeration</span><span class="sxs-lookup"><span data-stu-id="6a0b1-102">LoggingLevelEnum Enumeration</span></span>
<span data-ttu-id="6a0b1-103">Gibt den Schweregrad einer beschreibenden Meldung an, die in das Ereignisprotokoll geschrieben wird, wenn ein verwalteter Thread ein Ereignis protokolliert.</span><span class="sxs-lookup"><span data-stu-id="6a0b1-103">Indicates the severity level of a descriptive message that is written to the event log when a managed thread logs an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a0b1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6a0b1-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="6a0b1-105">Member</span><span class="sxs-lookup"><span data-stu-id="6a0b1-105">Members</span></span>  
  
|<span data-ttu-id="6a0b1-106">Member</span><span class="sxs-lookup"><span data-stu-id="6a0b1-106">Member</span></span>|<span data-ttu-id="6a0b1-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6a0b1-107">Description</span></span>|  
|------------|-----------------|  
|`LTraceLevel0`|<span data-ttu-id="6a0b1-108">Die Meldung ist eine Ablauf Verfolgungs Ebene von 0.</span><span class="sxs-lookup"><span data-stu-id="6a0b1-108">The message is a trace level 0.</span></span>|  
|`LTraceLevel1`|<span data-ttu-id="6a0b1-109">Die Meldung ist eine Ablauf Verfolgungs Ebene 1.</span><span class="sxs-lookup"><span data-stu-id="6a0b1-109">The message is a trace level 1.</span></span>|  
|`LTraceLevel2`|<span data-ttu-id="6a0b1-110">Die Meldung ist eine Ablauf Verfolgungs Ebene 2.</span><span class="sxs-lookup"><span data-stu-id="6a0b1-110">The message is a trace level 2.</span></span>|  
|`LTraceLevel3`|<span data-ttu-id="6a0b1-111">Die Meldung ist eine Ablauf Verfolgungs Ebene 3.</span><span class="sxs-lookup"><span data-stu-id="6a0b1-111">The message is a trace level 3.</span></span>|  
|`LTraceLevel4`|<span data-ttu-id="6a0b1-112">Die Meldung ist eine Ablauf Verfolgungs Ebene 4.</span><span class="sxs-lookup"><span data-stu-id="6a0b1-112">The message is a trace level 4.</span></span>|  
|`LStatusLevel0`|<span data-ttu-id="6a0b1-113">Die Meldung ist eine Status Ebene von 0.</span><span class="sxs-lookup"><span data-stu-id="6a0b1-113">The message is a status level 0.</span></span>|  
|`LStatusLevel1`|<span data-ttu-id="6a0b1-114">Die Meldung ist eine Status Ebene 1.</span><span class="sxs-lookup"><span data-stu-id="6a0b1-114">The message is a status level 1.</span></span>|  
|`LStatusLevel2`|<span data-ttu-id="6a0b1-115">Die Meldung ist eine Status Ebene 2.</span><span class="sxs-lookup"><span data-stu-id="6a0b1-115">The message is a status level 2.</span></span>|  
|`LStatusLevel3`|<span data-ttu-id="6a0b1-116">Die Meldung ist eine Status Ebene 3.</span><span class="sxs-lookup"><span data-stu-id="6a0b1-116">The message is a status level 3.</span></span>|  
|`LStatusLevel4`|<span data-ttu-id="6a0b1-117">Die Meldung ist eine Status Ebene 4.</span><span class="sxs-lookup"><span data-stu-id="6a0b1-117">The message is a status level 4.</span></span>|  
|`LWarningLevel`|<span data-ttu-id="6a0b1-118">Die Meldung ist eine Warnstufe.</span><span class="sxs-lookup"><span data-stu-id="6a0b1-118">The message is a warning level.</span></span>|  
|`LErrorLevel`|<span data-ttu-id="6a0b1-119">Die Meldung ist eine Fehler Ebene.</span><span class="sxs-lookup"><span data-stu-id="6a0b1-119">The message is an error level.</span></span>|  
|`LPanicLevel`|<span data-ttu-id="6a0b1-120">Die Meldung ist eine Panik Ebene.</span><span class="sxs-lookup"><span data-stu-id="6a0b1-120">The message is a panic level.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a0b1-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6a0b1-121">Remarks</span></span>  
 <span data-ttu-id="6a0b1-122">Der Common Language Runtime (CLR) Ruft die [ICorDebugManagedCallback:: LogMessage](icordebugmanagedcallback-logmessage-method.md) -Methode auf, um den Debugger zu benachrichtigen, dass ein verwalteter Thread ein Ereignis protokolliert hat.</span><span class="sxs-lookup"><span data-stu-id="6a0b1-122">The common language runtime (CLR) calls the [ICorDebugManagedCallback::LogMessage](icordebugmanagedcallback-logmessage-method.md) method to notify the debugger that a managed thread has logged an event.</span></span> <span data-ttu-id="6a0b1-123">Die CLR übergibt einen Wert der `LoggingLevelEnum`-Enumeration, um den Schweregrad der Meldung anzugeben, die der verwaltete Thread in das Ereignisprotokoll geschrieben hat.</span><span class="sxs-lookup"><span data-stu-id="6a0b1-123">The CLR passes a value of the `LoggingLevelEnum` enumeration to indicate the severity level of the message that the managed thread wrote to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a0b1-124">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6a0b1-124">Requirements</span></span>  
 <span data-ttu-id="6a0b1-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a0b1-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a0b1-126">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a0b1-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a0b1-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a0b1-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a0b1-128">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a0b1-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a0b1-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a0b1-129">See also</span></span>

- <xref:System.Diagnostics.EventLog>
- [<span data-ttu-id="6a0b1-130">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="6a0b1-130">Debugging Enumerations</span></span>](debugging-enumerations.md)
