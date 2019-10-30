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
ms.openlocfilehash: 739b491d343c0eba76160c15719069ffae385f46
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73097977"
---
# <a name="cordebugjitcompilerflags-enumeration"></a><span data-ttu-id="95bd5-102">CorDebugJITCompilerFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="95bd5-102">CorDebugJITCompilerFlags Enumeration</span></span>
<span data-ttu-id="95bd5-103">Enthält Werte, die das Verhalten des verwalteten JIT-Compilers (Just-In-Time) beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="95bd5-103">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95bd5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="95bd5-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="95bd5-105">Member</span><span class="sxs-lookup"><span data-stu-id="95bd5-105">Members</span></span>  
  
|<span data-ttu-id="95bd5-106">Member</span><span class="sxs-lookup"><span data-stu-id="95bd5-106">Member</span></span>|<span data-ttu-id="95bd5-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="95bd5-107">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|<span data-ttu-id="95bd5-108">Gibt an, dass der Compiler Kompilierungs Daten nachverfolgen und Optimierungen zulässt.</span><span class="sxs-lookup"><span data-stu-id="95bd5-108">Specifies that the compiler should track compilation data, and allows optimizations.</span></span>|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|<span data-ttu-id="95bd5-109">Gibt an, dass der Compiler Kompilierungs Daten nachverfolgen soll, aber Optimierungen deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="95bd5-109">Specifies that the compiler should track compilation data, but disables optimizations.</span></span>|  
|`CORDEBUG_JIT_ENABLE_ENC`|<span data-ttu-id="95bd5-110">Gibt an, dass der Compiler Kompilierungs Daten nachverfolgen, Optimierungen deaktiviert und die Technologien "Bearbeiten" und "Fortfahren" aktiviert.</span><span class="sxs-lookup"><span data-stu-id="95bd5-110">Specifies that the compiler should track compilation data, disables optimizations, and enables Edit and Continue technologies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="95bd5-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="95bd5-111">Requirements</span></span>  
 <span data-ttu-id="95bd5-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95bd5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95bd5-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95bd5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95bd5-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95bd5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95bd5-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95bd5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95bd5-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="95bd5-116">See also</span></span>

- [<span data-ttu-id="95bd5-117">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="95bd5-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
