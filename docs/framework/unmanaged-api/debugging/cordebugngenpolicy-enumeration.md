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
ms.openlocfilehash: de0e07429187f1ec484942d522cdf57f819d553a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789298"
---
# <a name="cordebugngenpolicy-enumeration"></a><span data-ttu-id="ae0cf-102">CorDebugNGenPolicy-Enumeration</span><span class="sxs-lookup"><span data-stu-id="ae0cf-102">CorDebugNGenPolicy Enumeration</span></span>
<span data-ttu-id="ae0cf-103">Stellt einen Wert bereit, der bestimmt, ob ein Debugger systemeigene Abbilder (NGen) aus dem Cache für systemeigene Abbilder lädt.</span><span class="sxs-lookup"><span data-stu-id="ae0cf-103">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae0cf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ae0cf-104">Syntax</span></span>  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="ae0cf-105">Member</span><span class="sxs-lookup"><span data-stu-id="ae0cf-105">Members</span></span>  
  
|<span data-ttu-id="ae0cf-106">Mitgliedsname</span><span class="sxs-lookup"><span data-stu-id="ae0cf-106">Member name</span></span>|<span data-ttu-id="ae0cf-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ae0cf-107">Description</span></span>|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|<span data-ttu-id="ae0cf-108">In einer Windows 8. x Store-App wird die Verwendung von Images aus dem lokalen Cache für Native Images deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="ae0cf-108">In a Windows 8.x Store app, the use of images from the local native image cache is disabled.</span></span> <span data-ttu-id="ae0cf-109">In einer Desktop-App hat diese Einstellung keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="ae0cf-109">In a desktop app, this setting has no effect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae0cf-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ae0cf-110">Remarks</span></span>  
 <span data-ttu-id="ae0cf-111">Die `CorDebugNGENPolicy`-Enumeration wird von der [ICorDebugProcess5:: enablengenpolicy](icordebugprocess5-enablengenpolicy-method.md) -Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="ae0cf-111">The `CorDebugNGENPolicy` enumeration is used by the [ICorDebugProcess5::EnableNGENPolicy](icordebugprocess5-enablengenpolicy-method.md) method.</span></span> <span data-ttu-id="ae0cf-112">Das Deaktivieren der Verwendung von Bildern aus dem lokalen Cache für systemeigene Images sorgt für ein konsistentes Debuggen, indem sichergestellt wird, dass der Debugger Debugfähige JIT-kompilierte Images anstelle von optimierten systemeigenen Images lädt.</span><span class="sxs-lookup"><span data-stu-id="ae0cf-112">Disabling the use of images from the local native image cache provides for a consistent debugging experience by ensuring that the debugger loads debuggable JIT-compiled images instead of optimized native images.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae0cf-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ae0cf-113">Requirements</span></span>  
 <span data-ttu-id="ae0cf-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae0cf-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae0cf-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae0cf-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae0cf-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae0cf-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae0cf-117">**.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae0cf-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae0cf-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae0cf-118">See also</span></span>

- [<span data-ttu-id="ae0cf-119">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="ae0cf-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
