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
ms.openlocfilehash: 8be8ce36b557831bc0997dd1c69abb924390d051
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795819"
---
# <a name="cordebugjitcompilerflags-enumeration"></a><span data-ttu-id="8c1c1-102">CorDebugJITCompilerFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="8c1c1-102">CorDebugJITCompilerFlags Enumeration</span></span>
<span data-ttu-id="8c1c1-103">Enthält Werte, die das Verhalten des verwalteten JIT-Compilers (Just-In-Time) beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="8c1c1-103">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c1c1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8c1c1-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="8c1c1-105">Member</span><span class="sxs-lookup"><span data-stu-id="8c1c1-105">Members</span></span>  
  
|<span data-ttu-id="8c1c1-106">Member</span><span class="sxs-lookup"><span data-stu-id="8c1c1-106">Member</span></span>|<span data-ttu-id="8c1c1-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8c1c1-107">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|<span data-ttu-id="8c1c1-108">Gibt an, dass der Compiler Kompilierungs Daten nachverfolgen und Optimierungen zulässt.</span><span class="sxs-lookup"><span data-stu-id="8c1c1-108">Specifies that the compiler should track compilation data, and allows optimizations.</span></span>|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|<span data-ttu-id="8c1c1-109">Gibt an, dass der Compiler Kompilierungs Daten nachverfolgen soll, aber Optimierungen deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="8c1c1-109">Specifies that the compiler should track compilation data, but disables optimizations.</span></span>|  
|`CORDEBUG_JIT_ENABLE_ENC`|<span data-ttu-id="8c1c1-110">Gibt an, dass der Compiler Kompilierungs Daten nachverfolgen, Optimierungen deaktiviert und die Technologien "Bearbeiten" und "Fortfahren" aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8c1c1-110">Specifies that the compiler should track compilation data, disables optimizations, and enables Edit and Continue technologies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8c1c1-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8c1c1-111">Requirements</span></span>  
 <span data-ttu-id="8c1c1-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c1c1-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c1c1-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c1c1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c1c1-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c1c1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c1c1-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c1c1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c1c1-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8c1c1-116">See also</span></span>

- [<span data-ttu-id="8c1c1-117">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="8c1c1-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
