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
ms.openlocfilehash: b7db7c9e17d87b91e09d5d010d40431cba5385df
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795988"
---
# <a name="cordebugdebugeventkind-enumeration"></a><span data-ttu-id="6bf8b-102">CorDebugDebugEventKind-Aufzählung</span><span class="sxs-lookup"><span data-stu-id="6bf8b-102">CorDebugDebugEventKind Enumeration</span></span>
<span data-ttu-id="6bf8b-103">Gibt den Typ des Ereignisses an, dessen Informationen von der [decodeevent](icordebugprocess6-decodeevent-method.md) -Methode decodiert werden.</span><span class="sxs-lookup"><span data-stu-id="6bf8b-103">Indicates the type of event whose information is decoded by the [DecodeEvent](icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bf8b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6bf8b-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="6bf8b-105">Member</span><span class="sxs-lookup"><span data-stu-id="6bf8b-105">Members</span></span>  
  
|<span data-ttu-id="6bf8b-106">Member</span><span class="sxs-lookup"><span data-stu-id="6bf8b-106">Member</span></span>|<span data-ttu-id="6bf8b-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6bf8b-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EVENT_KIND_MODULE_LOADED`|<span data-ttu-id="6bf8b-108">Ein Modullade-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="6bf8b-108">A module load event.</span></span>|  
|`DEBUG_EVENT_KIND_MODULE_UNLOADED`|<span data-ttu-id="6bf8b-109">Ein Modulentlade-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="6bf8b-109">A module unload event.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="6bf8b-110">Eine Ausnahme der ersten Chance.</span><span class="sxs-lookup"><span data-stu-id="6bf8b-110">A first-chance exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="6bf8b-111">Eine Benutzerausnahme der ersten Chance.</span><span class="sxs-lookup"><span data-stu-id="6bf8b-111">A first-chance user exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="6bf8b-112">Eine Ausnahme, für die ein `catch`-Handler vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="6bf8b-112">An exception for which a `catch` handler exists.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED`|<span data-ttu-id="6bf8b-113">Eine nicht behandelte Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="6bf8b-113">An unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6bf8b-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6bf8b-114">Remarks</span></span>  
 <span data-ttu-id="6bf8b-115">Ein Member der- `CorDebugDebugEventKind` Enumeration wird durch Aufrufen der [icordebugdebugevent:: geteventkind](icordebugdebugevent-geteventkind-method.md) -Methode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6bf8b-115">A member of the `CorDebugDebugEventKind` enumeration is returned by calling the [ICorDebugDebugEvent::GetEventKind](icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6bf8b-116">Diese Enumeration ist nur für die Verwendung in .NET Native-Debugszenarien vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="6bf8b-116">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bf8b-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6bf8b-117">Requirements</span></span>  
 <span data-ttu-id="6bf8b-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6bf8b-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bf8b-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6bf8b-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6bf8b-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6bf8b-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6bf8b-121">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bf8b-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bf8b-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6bf8b-122">See also</span></span>

- [<span data-ttu-id="6bf8b-123">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="6bf8b-123">Debugging Enumerations</span></span>](debugging-enumerations.md)
