---
title: CorDebugJITCompilerFlags-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugJITCompilerFlags
helpviewer_keywords:
- CorDebugJITCompilerFlags enumeration [.NET Framework debugging]
ms.assetid: c0774f70-5bed-45e8-9922-fdad778c4c33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 39bc1316bb7d8e2aba3390499437aadf263dac07
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739844"
---
# <a name="cordebugjitcompilerflags-enumeration"></a><span data-ttu-id="a2d47-102">CorDebugJITCompilerFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="a2d47-102">CorDebugJITCompilerFlags Enumeration</span></span>
<span data-ttu-id="a2d47-103">Enthält Werte, die das Verhalten des verwalteten JIT-Compilers (Just-In-Time) beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="a2d47-103">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2d47-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a2d47-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="a2d47-105">Member</span><span class="sxs-lookup"><span data-stu-id="a2d47-105">Members</span></span>  
  
|<span data-ttu-id="a2d47-106">Member</span><span class="sxs-lookup"><span data-stu-id="a2d47-106">Member</span></span>|<span data-ttu-id="a2d47-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2d47-107">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|<span data-ttu-id="a2d47-108">Gibt an, dass der Compiler Kompilierungsdaten nachverfolgen muss und Optimierungen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="a2d47-108">Specifies that the compiler should track compilation data, and allows optimizations.</span></span>|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|<span data-ttu-id="a2d47-109">Gibt an, dass der Compiler die Kompilierungsdaten, aber deaktiviert Optimierungen nachverfolgen muss.</span><span class="sxs-lookup"><span data-stu-id="a2d47-109">Specifies that the compiler should track compilation data, but disables optimizations.</span></span>|  
|`CORDEBUG_JIT_ENABLE_ENC`|<span data-ttu-id="a2d47-110">Gibt an, dass der Compiler die Kompilierungsdaten deaktiviert Optimierungen, nachverfolgen muss und ermöglicht das Bearbeiten und Technologien.</span><span class="sxs-lookup"><span data-stu-id="a2d47-110">Specifies that the compiler should track compilation data, disables optimizations, and enables Edit and Continue technologies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a2d47-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a2d47-111">Requirements</span></span>  
 <span data-ttu-id="a2d47-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2d47-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2d47-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2d47-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2d47-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2d47-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2d47-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2d47-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2d47-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2d47-116">See also</span></span>

- [<span data-ttu-id="a2d47-117">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="a2d47-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
