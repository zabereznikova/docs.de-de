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
ms.openlocfilehash: c7af194351290ad937e40a2fc8b960c2c242629c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132797"
---
# <a name="cordebugmdaflags-enumeration"></a><span data-ttu-id="03141-102">CorDebugMDAFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="03141-102">CorDebugMDAFlags Enumeration</span></span>
<span data-ttu-id="03141-103">Gibt den Status des Threads an, auf dem der Assistent für verwaltetes Debuggen (MDA) ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="03141-103">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03141-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="03141-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="03141-105">Member</span><span class="sxs-lookup"><span data-stu-id="03141-105">Members</span></span>  
  
|<span data-ttu-id="03141-106">Member</span><span class="sxs-lookup"><span data-stu-id="03141-106">Member</span></span>|<span data-ttu-id="03141-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="03141-107">Description</span></span>|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|<span data-ttu-id="03141-108">Der Thread, in dem der MDA ausgelöst wurde, wurde seit dem Auslösen des MDA zurückgezogen.</span><span class="sxs-lookup"><span data-stu-id="03141-108">The thread on which the MDA was fired has slipped since the MDA was fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03141-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="03141-109">Remarks</span></span>  
 <span data-ttu-id="03141-110">Wenn die-aufrufsstapel nicht mehr beschreibt, wo der MDA ursprünglich ausgelöst wurde, wird der Thread als *abgerutscht*angesehen.</span><span class="sxs-lookup"><span data-stu-id="03141-110">When the call stack no longer describes where the MDA was originally raised, the thread is considered to have *slipped*.</span></span> <span data-ttu-id="03141-111">Dies ist ein ungewöhnlicher Umstand, der durch die Ausführung eines ungültigen Vorgangs durch den Thread beim Beenden verursacht wird.</span><span class="sxs-lookup"><span data-stu-id="03141-111">This is an unusual circumstance brought about by the thread's execution of an invalid operation upon exiting.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03141-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="03141-112">Requirements</span></span>  
 <span data-ttu-id="03141-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03141-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03141-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03141-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03141-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03141-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03141-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03141-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03141-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03141-117">See also</span></span>

- [<span data-ttu-id="03141-118">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="03141-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
