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
ms.openlocfilehash: e024500ea66dcb42e712e07e976a709401160a27
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795767"
---
# <a name="cordebugmdaflags-enumeration"></a><span data-ttu-id="9d057-102">CorDebugMDAFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="9d057-102">CorDebugMDAFlags Enumeration</span></span>
<span data-ttu-id="9d057-103">Gibt den Status des Threads an, auf dem der Assistent für verwaltetes Debuggen (MDA) ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="9d057-103">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d057-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d057-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="9d057-105">Member</span><span class="sxs-lookup"><span data-stu-id="9d057-105">Members</span></span>  
  
|<span data-ttu-id="9d057-106">Member</span><span class="sxs-lookup"><span data-stu-id="9d057-106">Member</span></span>|<span data-ttu-id="9d057-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9d057-107">Description</span></span>|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|<span data-ttu-id="9d057-108">Der Thread, in dem der MDA ausgelöst wurde, wurde seit dem Auslösen des MDA zurückgezogen.</span><span class="sxs-lookup"><span data-stu-id="9d057-108">The thread on which the MDA was fired has slipped since the MDA was fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d057-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9d057-109">Remarks</span></span>  
 <span data-ttu-id="9d057-110">Wenn die-aufrufsstapel nicht mehr beschreibt, wo der MDA ursprünglich ausgelöst wurde, wird der Thread als *abgerutscht*angesehen.</span><span class="sxs-lookup"><span data-stu-id="9d057-110">When the call stack no longer describes where the MDA was originally raised, the thread is considered to have *slipped*.</span></span> <span data-ttu-id="9d057-111">Dies ist ein ungewöhnlicher Umstand, der durch die Ausführung eines ungültigen Vorgangs durch den Thread beim Beenden verursacht wird.</span><span class="sxs-lookup"><span data-stu-id="9d057-111">This is an unusual circumstance brought about by the thread's execution of an invalid operation upon exiting.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d057-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9d057-112">Requirements</span></span>  
 <span data-ttu-id="9d057-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d057-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d057-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d057-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d057-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d057-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d057-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d057-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d057-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9d057-117">See also</span></span>

- [<span data-ttu-id="9d057-118">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="9d057-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
