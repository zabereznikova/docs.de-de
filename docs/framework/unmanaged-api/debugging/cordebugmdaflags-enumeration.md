---
title: CorDebugMDAFlags-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugMDAFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMDAFlags
helpviewer_keywords:
- CorDebugMDAFlags enumeration [.NET Framework debugging]
ms.assetid: 7c0c92fe-8bd2-477f-b307-aca0143732ca
topic_type:
- apiref
ms.openlocfilehash: 1bb99503481d917d41ae00a5ef73c8fa59e2a999
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696452"
---
# <a name="cordebugmdaflags-enumeration"></a><span data-ttu-id="e4a76-102">CorDebugMDAFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e4a76-102">CorDebugMDAFlags Enumeration</span></span>

<span data-ttu-id="e4a76-103">Gibt den Status des Threads an, auf dem der Assistent für verwaltetes Debuggen (MDA) ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="e4a76-103">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4a76-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4a76-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="e4a76-105">Member</span><span class="sxs-lookup"><span data-stu-id="e4a76-105">Members</span></span>  
  
|<span data-ttu-id="e4a76-106">Member</span><span class="sxs-lookup"><span data-stu-id="e4a76-106">Member</span></span>|<span data-ttu-id="e4a76-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e4a76-107">Description</span></span>|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|<span data-ttu-id="e4a76-108">Der Thread, in dem der MDA ausgelöst wurde, wurde seit dem Auslösen des MDA zurückgezogen.</span><span class="sxs-lookup"><span data-stu-id="e4a76-108">The thread on which the MDA was fired has slipped since the MDA was fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4a76-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e4a76-109">Remarks</span></span>  

 <span data-ttu-id="e4a76-110">Wenn die-aufrufsstapel nicht mehr beschreibt, wo der MDA ursprünglich ausgelöst wurde, wird der Thread als *abgerutscht* angesehen.</span><span class="sxs-lookup"><span data-stu-id="e4a76-110">When the call stack no longer describes where the MDA was originally raised, the thread is considered to have *slipped*.</span></span> <span data-ttu-id="e4a76-111">Dies ist ein ungewöhnlicher Umstand, der durch die Ausführung eines ungültigen Vorgangs durch den Thread beim Beenden verursacht wird.</span><span class="sxs-lookup"><span data-stu-id="e4a76-111">This is an unusual circumstance brought about by the thread's execution of an invalid operation upon exiting.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4a76-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e4a76-112">Requirements</span></span>  

 <span data-ttu-id="e4a76-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4a76-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4a76-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4a76-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4a76-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4a76-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4a76-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4a76-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4a76-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e4a76-117">See also</span></span>

- [<span data-ttu-id="e4a76-118">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="e4a76-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
