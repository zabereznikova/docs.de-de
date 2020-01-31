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
ms.openlocfilehash: 65d7e830b82cc1780826517fe8cff1da0a7d6188
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793893"
---
# <a name="cordebugjitcompilerflags-enumeration"></a><span data-ttu-id="7b543-102">CorDebugJITCompilerFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7b543-102">CorDebugJITCompilerFlags Enumeration</span></span>
<span data-ttu-id="7b543-103">Enthält Werte, die das Verhalten des verwalteten JIT-Compilers (Just-In-Time) beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="7b543-103">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b543-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7b543-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="7b543-105">Member</span><span class="sxs-lookup"><span data-stu-id="7b543-105">Members</span></span>  
  
|<span data-ttu-id="7b543-106">Member</span><span class="sxs-lookup"><span data-stu-id="7b543-106">Member</span></span>|<span data-ttu-id="7b543-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b543-107">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|<span data-ttu-id="7b543-108">Gibt an, dass der Compiler Kompilierungs Daten nachverfolgen und Optimierungen zulässt.</span><span class="sxs-lookup"><span data-stu-id="7b543-108">Specifies that the compiler should track compilation data, and allows optimizations.</span></span>|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|<span data-ttu-id="7b543-109">Gibt an, dass der Compiler Kompilierungs Daten nachverfolgen soll, aber Optimierungen deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="7b543-109">Specifies that the compiler should track compilation data, but disables optimizations.</span></span>|  
|`CORDEBUG_JIT_ENABLE_ENC`|<span data-ttu-id="7b543-110">Gibt an, dass der Compiler Kompilierungs Daten nachverfolgen, Optimierungen deaktiviert und die Technologien "Bearbeiten" und "Fortfahren" aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7b543-110">Specifies that the compiler should track compilation data, disables optimizations, and enables Edit and Continue technologies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7b543-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7b543-111">Requirements</span></span>  
 <span data-ttu-id="7b543-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b543-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b543-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b543-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b543-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b543-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b543-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b543-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b543-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b543-116">See also</span></span>

- [<span data-ttu-id="7b543-117">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="7b543-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
