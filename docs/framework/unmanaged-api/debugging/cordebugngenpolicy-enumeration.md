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
ms.openlocfilehash: ca922d8b582c0608073d4fd0ba986167ae470e34
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61599503"
---
# <a name="cordebugngenpolicy-enumeration"></a><span data-ttu-id="d1b0c-102">CorDebugNGenPolicy-Enumeration</span><span class="sxs-lookup"><span data-stu-id="d1b0c-102">CorDebugNGenPolicy Enumeration</span></span>
<span data-ttu-id="d1b0c-103">Stellt einen Wert bereit, der bestimmt, ob ein Debugger systemeigene Abbilder (NGen) aus dem Cache für systemeigene Abbilder lädt.</span><span class="sxs-lookup"><span data-stu-id="d1b0c-103">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1b0c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d1b0c-104">Syntax</span></span>  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="d1b0c-105">Member</span><span class="sxs-lookup"><span data-stu-id="d1b0c-105">Members</span></span>  
  
|<span data-ttu-id="d1b0c-106">Membername</span><span class="sxs-lookup"><span data-stu-id="d1b0c-106">Member name</span></span>|<span data-ttu-id="d1b0c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d1b0c-107">Description</span></span>|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|<span data-ttu-id="d1b0c-108">In einem [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] -app, die Verwendung von Bildern aus dem lokalen nativen Imagecache deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d1b0c-108">In a [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] app, the use of images from the local native image cache is disabled.</span></span> <span data-ttu-id="d1b0c-109">In einer desktop-app hat diese Einstellung keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="d1b0c-109">In a desktop app, this setting has no effect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1b0c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d1b0c-110">Remarks</span></span>  
 <span data-ttu-id="d1b0c-111">Die `CorDebugNGENPolicy` Enumeration wird verwendet, durch die [icordebugprocess5:: Enablengenpolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="d1b0c-111">The `CorDebugNGENPolicy` enumeration is used by the [ICorDebugProcess5::EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) method.</span></span> <span data-ttu-id="d1b0c-112">Deaktivieren die Verwendung von Bildern aus dem lokalen nativen Imagecache bietet eine einheitliche Debugleistung erzielen Sie sicherstellen, dass der Debugger debuggt JIT-kompilierten Bilder statt optimierte systemeigene Abbilder lädt.</span><span class="sxs-lookup"><span data-stu-id="d1b0c-112">Disabling the use of images from the local native image cache provides for a consistent debugging experience by ensuring that the debugger loads debuggable JIT-compiled images instead of optimized native images.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1b0c-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d1b0c-113">Requirements</span></span>  
 <span data-ttu-id="d1b0c-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1b0c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1b0c-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1b0c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1b0c-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1b0c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1b0c-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1b0c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1b0c-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1b0c-118">See also</span></span>

- [<span data-ttu-id="d1b0c-119">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="d1b0c-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
