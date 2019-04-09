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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109667"
---
# <a name="cordebugngenpolicy-enumeration"></a><span data-ttu-id="b9a66-102">CorDebugNGenPolicy-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b9a66-102">CorDebugNGenPolicy Enumeration</span></span>
<span data-ttu-id="b9a66-103">Stellt einen Wert bereit, der bestimmt, ob ein Debugger systemeigene Abbilder (NGen) aus dem Cache für systemeigene Abbilder lädt.</span><span class="sxs-lookup"><span data-stu-id="b9a66-103">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9a66-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b9a66-104">Syntax</span></span>  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="b9a66-105">Member</span><span class="sxs-lookup"><span data-stu-id="b9a66-105">Members</span></span>  
  
|<span data-ttu-id="b9a66-106">Membername</span><span class="sxs-lookup"><span data-stu-id="b9a66-106">Member name</span></span>|<span data-ttu-id="b9a66-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9a66-107">Description</span></span>|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|<span data-ttu-id="b9a66-108">In einem [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] -app, die Verwendung von Bildern aus dem lokalen nativen Imagecache deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b9a66-108">In a [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] app, the use of images from the local native image cache is disabled.</span></span> <span data-ttu-id="b9a66-109">In einer desktop-app hat diese Einstellung keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="b9a66-109">In a desktop app, this setting has no effect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9a66-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b9a66-110">Remarks</span></span>  
 <span data-ttu-id="b9a66-111">Die `CorDebugNGENPolicy` Enumeration wird verwendet, durch die [icordebugprocess5:: Enablengenpolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="b9a66-111">The `CorDebugNGENPolicy` enumeration is used by the [ICorDebugProcess5::EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) method.</span></span> <span data-ttu-id="b9a66-112">Deaktivieren die Verwendung von Bildern aus dem lokalen nativen Imagecache bietet eine einheitliche Debugleistung erzielen Sie sicherstellen, dass der Debugger debuggt JIT-kompilierten Bilder statt optimierte systemeigene Abbilder lädt.</span><span class="sxs-lookup"><span data-stu-id="b9a66-112">Disabling the use of images from the local native image cache provides for a consistent debugging experience by ensuring that the debugger loads debuggable JIT-compiled images instead of optimized native images.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9a66-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b9a66-113">Requirements</span></span>  
 <span data-ttu-id="b9a66-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9a66-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9a66-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9a66-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9a66-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9a66-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b9a66-117">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="b9a66-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b9a66-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9a66-118">See also</span></span>

- [<span data-ttu-id="b9a66-119">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="b9a66-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
