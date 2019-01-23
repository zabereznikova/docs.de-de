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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83cee30ed9831accb96de17768f63e7f401908f0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54495951"
---
# <a name="cordebugcreateprocessflags-enumeration"></a><span data-ttu-id="6c59e-102">CorDebugCreateProcessFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="6c59e-102">CorDebugCreateProcessFlags Enumeration</span></span>
<span data-ttu-id="6c59e-103">Stellt zusätzliche Debuggingoptionen, die in einem Aufruf verwendet werden, können die [ICorDebug:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="6c59e-103">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c59e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c59e-104">Syntax</span></span>  
  
```  
typedef enum CorDebugCreateProcessFlags {  
    DEBUG_NO_SPECIAL_OPTIONS    = 0x0000  
} CorDebugCreateProcessFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="6c59e-105">Member</span><span class="sxs-lookup"><span data-stu-id="6c59e-105">Members</span></span>  
  
|<span data-ttu-id="6c59e-106">Member</span><span class="sxs-lookup"><span data-stu-id="6c59e-106">Member</span></span>|<span data-ttu-id="6c59e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c59e-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_NO_SPECIAL_OPTIONS`|<span data-ttu-id="6c59e-108">Es werden keine besonderen Optionen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6c59e-108">No special options are set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6c59e-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6c59e-109">Requirements</span></span>  
 <span data-ttu-id="6c59e-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c59e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c59e-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6c59e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6c59e-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c59e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c59e-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c59e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c59e-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c59e-114">See also</span></span>
- [<span data-ttu-id="6c59e-115">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="6c59e-115">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
