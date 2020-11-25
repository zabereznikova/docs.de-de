---
title: CorDebugNGenPolicy-Enumeration
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugNGenPolicy
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugNGenPolicy
helpviewer_keywords:
- CorDebugNgenPolicy enumeration [.NET Framework debugging]
ms.assetid: edb4e4d2-3166-44d4-8b17-bf302f7ea093
topic_type:
- apiref
ms.openlocfilehash: b64de0fa2ecbddd2decf69a4099d9897ec42a563
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696426"
---
# <a name="cordebugngenpolicy-enumeration"></a><span data-ttu-id="ecaff-102">CorDebugNGenPolicy-Enumeration</span><span class="sxs-lookup"><span data-stu-id="ecaff-102">CorDebugNGenPolicy Enumeration</span></span>

<span data-ttu-id="ecaff-103">Stellt einen Wert bereit, der bestimmt, ob ein Debugger systemeigene Abbilder (NGen) aus dem Cache für systemeigene Abbilder lädt.</span><span class="sxs-lookup"><span data-stu-id="ecaff-103">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecaff-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ecaff-104">Syntax</span></span>  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="ecaff-105">Member</span><span class="sxs-lookup"><span data-stu-id="ecaff-105">Members</span></span>  
  
|<span data-ttu-id="ecaff-106">Membername</span><span class="sxs-lookup"><span data-stu-id="ecaff-106">Member name</span></span>|<span data-ttu-id="ecaff-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ecaff-107">Description</span></span>|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|<span data-ttu-id="ecaff-108">In einer Windows 8. x Store-App wird die Verwendung von Images aus dem lokalen Cache für Native Images deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="ecaff-108">In a Windows 8.x Store app, the use of images from the local native image cache is disabled.</span></span> <span data-ttu-id="ecaff-109">In einer Desktop-App hat diese Einstellung keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="ecaff-109">In a desktop app, this setting has no effect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ecaff-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ecaff-110">Remarks</span></span>  

 <span data-ttu-id="ecaff-111">Die- `CorDebugNGENPolicy` Enumeration wird von der [ICorDebugProcess5:: enablengenpolicy](icordebugprocess5-enablengenpolicy-method.md) -Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="ecaff-111">The `CorDebugNGENPolicy` enumeration is used by the [ICorDebugProcess5::EnableNGENPolicy](icordebugprocess5-enablengenpolicy-method.md) method.</span></span> <span data-ttu-id="ecaff-112">Das Deaktivieren der Verwendung von Bildern aus dem lokalen Cache für systemeigene Images sorgt für ein konsistentes Debuggen, indem sichergestellt wird, dass der Debugger Debugfähige JIT-kompilierte Images anstelle von optimierten systemeigenen Images lädt.</span><span class="sxs-lookup"><span data-stu-id="ecaff-112">Disabling the use of images from the local native image cache provides for a consistent debugging experience by ensuring that the debugger loads debuggable JIT-compiled images instead of optimized native images.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecaff-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ecaff-113">Requirements</span></span>  

 <span data-ttu-id="ecaff-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecaff-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecaff-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ecaff-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ecaff-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecaff-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecaff-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecaff-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecaff-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ecaff-118">See also</span></span>

- [<span data-ttu-id="ecaff-119">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="ecaff-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
