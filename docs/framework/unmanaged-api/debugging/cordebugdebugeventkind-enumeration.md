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
ms.openlocfilehash: de4ac1f39ea9cfb4b616bd4e2c85e5de530dbb0b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132228"
---
# <a name="cordebugdebugeventkind-enumeration"></a><span data-ttu-id="f85ff-102">CorDebugDebugEventKind-Aufzählung</span><span class="sxs-lookup"><span data-stu-id="f85ff-102">CorDebugDebugEventKind Enumeration</span></span>
<span data-ttu-id="f85ff-103">Gibt den Typ des Ereignisses an, dessen Informationen von der [decodeevent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) -Methode decodiert werden.</span><span class="sxs-lookup"><span data-stu-id="f85ff-103">Indicates the type of event whose information is decoded by the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f85ff-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f85ff-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugDebugEventKind {  
    DEBUG_EVENT_KIND_MODULE_LOADED                          = 1,  
    DEBUG_EVENT_KIND_MODULE_UNLOADED                        = 2,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE         = 3,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE    = 4,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND  = 5,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED            = 6  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="f85ff-105">Member</span><span class="sxs-lookup"><span data-stu-id="f85ff-105">Members</span></span>  
  
|<span data-ttu-id="f85ff-106">Member</span><span class="sxs-lookup"><span data-stu-id="f85ff-106">Member</span></span>|<span data-ttu-id="f85ff-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f85ff-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EVENT_KIND_MODULE_LOADED`|<span data-ttu-id="f85ff-108">Ein Modullade-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="f85ff-108">A module load event.</span></span>|  
|`DEBUG_EVENT_KIND_MODULE_UNLOADED`|<span data-ttu-id="f85ff-109">Ein Modulentlade-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="f85ff-109">A module unload event.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="f85ff-110">Eine Ausnahme der ersten Chance.</span><span class="sxs-lookup"><span data-stu-id="f85ff-110">A first-chance exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="f85ff-111">Eine Benutzerausnahme der ersten Chance.</span><span class="sxs-lookup"><span data-stu-id="f85ff-111">A first-chance user exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="f85ff-112">Eine Ausnahme, für die ein `catch`-Handler vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f85ff-112">An exception for which a `catch` handler exists.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED`|<span data-ttu-id="f85ff-113">Eine nicht behandelte Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="f85ff-113">An unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f85ff-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f85ff-114">Remarks</span></span>  
 <span data-ttu-id="f85ff-115">Ein Member der `CorDebugDebugEventKind` Enumeration wird durch Aufrufen der [icordebugdebugevent:: geteventkind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) -Methode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f85ff-115">A member of the `CorDebugDebugEventKind` enumeration is returned by calling the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f85ff-116">Diese Enumeration ist nur für die Verwendung in .NET Native-Debugszenarien vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="f85ff-116">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f85ff-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f85ff-117">Requirements</span></span>  
 <span data-ttu-id="f85ff-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f85ff-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f85ff-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f85ff-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f85ff-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f85ff-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f85ff-121">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f85ff-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f85ff-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f85ff-122">See also</span></span>

- [<span data-ttu-id="f85ff-123">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="f85ff-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
