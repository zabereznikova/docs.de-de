---
title: CorDebugCreateProcessFlags-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugCreateProcessFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugCreateProcessFlags
helpviewer_keywords:
- CorDebugCreateProcessFlags enumeration [.NET Framework debugging]
ms.assetid: e709acce-6a17-4346-b38a-467dba567358
topic_type:
- apiref
ms.openlocfilehash: d28f6eab5390194a4089cbbaf1f586c3f53a7db5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132258"
---
# <a name="cordebugcreateprocessflags-enumeration"></a><span data-ttu-id="b3ee4-102">CorDebugCreateProcessFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b3ee4-102">CorDebugCreateProcessFlags Enumeration</span></span>
<span data-ttu-id="b3ee4-103">Bietet zusätzliche Debugoptionen, die in einem Aufrufen der [ICorDebug:: deateprocess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) -Methode verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="b3ee4-103">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3ee4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b3ee4-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugCreateProcessFlags {  
    DEBUG_NO_SPECIAL_OPTIONS    = 0x0000  
} CorDebugCreateProcessFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="b3ee4-105">Member</span><span class="sxs-lookup"><span data-stu-id="b3ee4-105">Members</span></span>  
  
|<span data-ttu-id="b3ee4-106">Member</span><span class="sxs-lookup"><span data-stu-id="b3ee4-106">Member</span></span>|<span data-ttu-id="b3ee4-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3ee4-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_NO_SPECIAL_OPTIONS`|<span data-ttu-id="b3ee4-108">Es sind keine besonderen Optionen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b3ee4-108">No special options are set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b3ee4-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b3ee4-109">Requirements</span></span>  
 <span data-ttu-id="b3ee4-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3ee4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3ee4-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b3ee4-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b3ee4-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3ee4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3ee4-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3ee4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3ee4-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3ee4-114">See also</span></span>

- [<span data-ttu-id="b3ee4-115">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="b3ee4-115">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
