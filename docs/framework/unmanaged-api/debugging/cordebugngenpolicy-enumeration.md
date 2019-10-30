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
ms.openlocfilehash: 826dfceb28512e4fd3157c432b7a4d94fba704fd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73097858"
---
# <a name="cordebugngenpolicy-enumeration"></a><span data-ttu-id="562b6-102">CorDebugNGenPolicy-Enumeration</span><span class="sxs-lookup"><span data-stu-id="562b6-102">CorDebugNGenPolicy Enumeration</span></span>
<span data-ttu-id="562b6-103">Stellt einen Wert bereit, der bestimmt, ob ein Debugger systemeigene Abbilder (NGen) aus dem Cache für systemeigene Abbilder lädt.</span><span class="sxs-lookup"><span data-stu-id="562b6-103">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="562b6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="562b6-104">Syntax</span></span>  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="562b6-105">Member</span><span class="sxs-lookup"><span data-stu-id="562b6-105">Members</span></span>  
  
|<span data-ttu-id="562b6-106">Membername</span><span class="sxs-lookup"><span data-stu-id="562b6-106">Member name</span></span>|<span data-ttu-id="562b6-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="562b6-107">Description</span></span>|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|<span data-ttu-id="562b6-108">In einer [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)]-APP wird die Verwendung von Images aus dem lokalen Cache für Native Images deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="562b6-108">In a [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] app, the use of images from the local native image cache is disabled.</span></span> <span data-ttu-id="562b6-109">In einer Desktop-App hat diese Einstellung keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="562b6-109">In a desktop app, this setting has no effect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="562b6-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="562b6-110">Remarks</span></span>  
 <span data-ttu-id="562b6-111">Die `CorDebugNGENPolicy`-Enumeration wird von der [ICorDebugProcess5:: enablengenpolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) -Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="562b6-111">The `CorDebugNGENPolicy` enumeration is used by the [ICorDebugProcess5::EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) method.</span></span> <span data-ttu-id="562b6-112">Das Deaktivieren der Verwendung von Bildern aus dem lokalen Cache für systemeigene Images sorgt für ein konsistentes Debuggen, indem sichergestellt wird, dass der Debugger Debugfähige JIT-kompilierte Images anstelle von optimierten systemeigenen Images lädt.</span><span class="sxs-lookup"><span data-stu-id="562b6-112">Disabling the use of images from the local native image cache provides for a consistent debugging experience by ensuring that the debugger loads debuggable JIT-compiled images instead of optimized native images.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="562b6-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="562b6-113">Requirements</span></span>  
 <span data-ttu-id="562b6-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="562b6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="562b6-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="562b6-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="562b6-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="562b6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="562b6-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="562b6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="562b6-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="562b6-118">See also</span></span>

- [<span data-ttu-id="562b6-119">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="562b6-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
