---
title: CorDebugMDAFlags-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugMDAFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugMDAFlags
helpviewer_keywords: CorDebugMDAFlags enumeration [.NET Framework debugging]
ms.assetid: 7c0c92fe-8bd2-477f-b307-aca0143732ca
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 827825e4012b421caa4e05702a6f1a1b863ac69d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugmdaflags-enumeration"></a><span data-ttu-id="c8b06-102">CorDebugMDAFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c8b06-102">CorDebugMDAFlags Enumeration</span></span>
<span data-ttu-id="c8b06-103">Gibt den Status des Threads an, auf dem der Assistent für verwaltetes Debuggen (MDA) ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="c8b06-103">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8b06-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8b06-104">Syntax</span></span>  
  
```  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="c8b06-105">Member</span><span class="sxs-lookup"><span data-stu-id="c8b06-105">Members</span></span>  
  
|<span data-ttu-id="c8b06-106">Member</span><span class="sxs-lookup"><span data-stu-id="c8b06-106">Member</span></span>|<span data-ttu-id="c8b06-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8b06-107">Description</span></span>|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|<span data-ttu-id="c8b06-108">Der Thread, auf dem der MDA ausgelöst wurde, verzögert ist seit dem Auslösen des MDA.</span><span class="sxs-lookup"><span data-stu-id="c8b06-108">The thread on which the MDA was fired has slipped since the MDA was fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8b06-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c8b06-109">Remarks</span></span>  
 <span data-ttu-id="c8b06-110">Wenn die Aufrufliste nicht mehr beschreibt, wo der MDA ursprünglich ausgelöst wurde, wird der Thread haben betrachtet *verlegt*.</span><span class="sxs-lookup"><span data-stu-id="c8b06-110">When the call stack no longer describes where the MDA was originally raised, the thread is considered to have *slipped*.</span></span> <span data-ttu-id="c8b06-111">Dies ist ein ungewöhnlichen Situation durch die Ausführung einen ungültigen Vorgang beim Beenden des Threads gebracht.</span><span class="sxs-lookup"><span data-stu-id="c8b06-111">This is an unusual circumstance brought about by the thread's execution of an invalid operation upon exiting.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8b06-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c8b06-112">Requirements</span></span>  
 <span data-ttu-id="c8b06-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8b06-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8b06-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8b06-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8b06-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8b06-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8b06-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8b06-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8b06-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8b06-117">See Also</span></span>  
 [<span data-ttu-id="c8b06-118">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="c8b06-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
