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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cc5a06e6b3cc1e9338d860cdb110bf7d516080be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404023"
---
# <a name="cordebugngenpolicy-enumeration"></a><span data-ttu-id="330ca-102">CorDebugNGenPolicy-Enumeration</span><span class="sxs-lookup"><span data-stu-id="330ca-102">CorDebugNGenPolicy Enumeration</span></span>
<span data-ttu-id="330ca-103">Stellt einen Wert bereit, der bestimmt, ob ein Debugger systemeigene Abbilder (NGen) aus dem Cache für systemeigene Abbilder lädt.</span><span class="sxs-lookup"><span data-stu-id="330ca-103">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="330ca-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="330ca-104">Syntax</span></span>  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="330ca-105">Member</span><span class="sxs-lookup"><span data-stu-id="330ca-105">Members</span></span>  
  
|<span data-ttu-id="330ca-106">Membername</span><span class="sxs-lookup"><span data-stu-id="330ca-106">Member name</span></span>|<span data-ttu-id="330ca-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="330ca-107">Description</span></span>|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|<span data-ttu-id="330ca-108">In einem [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] app, die Verwendung von Bildern aus dem lokalen systemeigenen Imagecache deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="330ca-108">In a [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] app, the use of images from the local native image cache is disabled.</span></span> <span data-ttu-id="330ca-109">In einer desktop-app hat diese Einstellung keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="330ca-109">In a desktop app, this setting has no effect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="330ca-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="330ca-110">Remarks</span></span>  
 <span data-ttu-id="330ca-111">Die `CorDebugNGENPolicy` Enumeration wird verwendet, durch die [icordebugprocess5:: Enablengenpolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="330ca-111">The `CorDebugNGENPolicy` enumeration is used by the [ICorDebugProcess5::EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) method.</span></span> <span data-ttu-id="330ca-112">Deaktivieren die Verwendung von Bildern aus dem lokalen systemeigenen Imagecache bietet eine konsistente Debugleistung erzielen, indem sichergestellt wird, dass der Debugger debugfähig JIT-kompilierten Bilder statt optimierte systemeigene Abbilder lädt.</span><span class="sxs-lookup"><span data-stu-id="330ca-112">Disabling the use of images from the local native image cache provides for a consistent debugging experience by ensuring that the debugger loads debuggable JIT-compiled images instead of optimized native images.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="330ca-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="330ca-113">Requirements</span></span>  
 <span data-ttu-id="330ca-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="330ca-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="330ca-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="330ca-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="330ca-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="330ca-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="330ca-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="330ca-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="330ca-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="330ca-118">See Also</span></span>  
 [<span data-ttu-id="330ca-119">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="330ca-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
