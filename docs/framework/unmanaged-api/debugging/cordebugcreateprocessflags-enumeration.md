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
ms.openlocfilehash: f6f589656a3063fc89bd276b32d0ed751fd8d2d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733398"
---
# <a name="cordebugcreateprocessflags-enumeration"></a><span data-ttu-id="19188-102">CorDebugCreateProcessFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="19188-102">CorDebugCreateProcessFlags Enumeration</span></span>

<span data-ttu-id="19188-103">Bietet zusätzliche Debugoptionen, die in einem Aufrufen der [ICorDebug:: deateprocess](icordebug-createprocess-method.md) -Methode verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="19188-103">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](icordebug-createprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19188-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="19188-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugCreateProcessFlags {  
    DEBUG_NO_SPECIAL_OPTIONS    = 0x0000  
} CorDebugCreateProcessFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="19188-105">Member</span><span class="sxs-lookup"><span data-stu-id="19188-105">Members</span></span>  
  
|<span data-ttu-id="19188-106">Member</span><span class="sxs-lookup"><span data-stu-id="19188-106">Member</span></span>|<span data-ttu-id="19188-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="19188-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_NO_SPECIAL_OPTIONS`|<span data-ttu-id="19188-108">Es sind keine besonderen Optionen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="19188-108">No special options are set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="19188-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="19188-109">Requirements</span></span>  

 <span data-ttu-id="19188-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19188-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19188-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="19188-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19188-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19188-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19188-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19188-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19188-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="19188-114">See also</span></span>

- [<span data-ttu-id="19188-115">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="19188-115">Debugging Enumerations</span></span>](debugging-enumerations.md)
