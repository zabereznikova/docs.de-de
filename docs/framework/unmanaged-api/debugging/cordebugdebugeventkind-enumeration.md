---
title: CorDebugDebugEventKind-Aufzählung
ms.date: 03/30/2017
api_name:
- CorDebugDebugEventKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6075a6cd-97e6-4472-a090-0dd14860d1f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e5479fad3f19c219a0ca1d5d01934ce92a7162e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127164"
---
# <a name="cordebugdebugeventkind-enumeration"></a><span data-ttu-id="bcb4a-102">CorDebugDebugEventKind-Aufzählung</span><span class="sxs-lookup"><span data-stu-id="bcb4a-102">CorDebugDebugEventKind Enumeration</span></span>
<span data-ttu-id="bcb4a-103">Gibt den Typ des Ereignisses, dessen Informationen decodiert wird, die [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="bcb4a-103">Indicates the type of event whose information is decoded by the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcb4a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bcb4a-104">Syntax</span></span>  
  
```  
typedef enum CorDebugDebugEventKind {  
    DEBUG_EVENT_KIND_MODULE_LOADED                          = 1,  
    DEBUG_EVENT_KIND_MODULE_UNLOADED                        = 2,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE         = 3,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE    = 4,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND  = 5,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED            = 6  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="bcb4a-105">Member</span><span class="sxs-lookup"><span data-stu-id="bcb4a-105">Members</span></span>  
  
|<span data-ttu-id="bcb4a-106">Member</span><span class="sxs-lookup"><span data-stu-id="bcb4a-106">Member</span></span>|<span data-ttu-id="bcb4a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bcb4a-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EVENT_KIND_MODULE_LOADED`|<span data-ttu-id="bcb4a-108">Ein Modullade-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="bcb4a-108">A module load event.</span></span>|  
|`DEBUG_EVENT_KIND_MODULE_UNLOADED`|<span data-ttu-id="bcb4a-109">Ein Modulentlade-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="bcb4a-109">A module unload event.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="bcb4a-110">Eine Ausnahme der ersten Chance.</span><span class="sxs-lookup"><span data-stu-id="bcb4a-110">A first-chance exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="bcb4a-111">Eine Benutzerausnahme der ersten Chance.</span><span class="sxs-lookup"><span data-stu-id="bcb4a-111">A first-chance user exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="bcb4a-112">Eine Ausnahme, für die ein `catch`-Handler vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="bcb4a-112">An exception for which a `catch` handler exists.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED`|<span data-ttu-id="bcb4a-113">Eine nicht behandelte Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="bcb4a-113">An unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bcb4a-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bcb4a-114">Remarks</span></span>  
 <span data-ttu-id="bcb4a-115">Ein Mitglied der `CorDebugDebugEventKind` Enumeration wird zurückgegeben, indem die [icordebugdebugevent:: Geteventkind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="bcb4a-115">A member of the `CorDebugDebugEventKind` enumeration is returned by calling the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bcb4a-116">Diese Enumeration ist nur für die Verwendung in .NET Native-Debugszenarien vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="bcb4a-116">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcb4a-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bcb4a-117">Requirements</span></span>  
 <span data-ttu-id="bcb4a-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcb4a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcb4a-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bcb4a-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bcb4a-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bcb4a-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="bcb4a-121">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="bcb4a-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bcb4a-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bcb4a-122">See also</span></span>

- [<span data-ttu-id="bcb4a-123">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="bcb4a-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
