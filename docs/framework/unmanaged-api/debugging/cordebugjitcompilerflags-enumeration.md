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
ms.openlocfilehash: 0c8398b9e423414f32a391edcd5ea1c709af37f5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696556"
---
# <a name="cordebugjitcompilerflags-enumeration"></a><span data-ttu-id="395da-102">CorDebugJITCompilerFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="395da-102">CorDebugJITCompilerFlags Enumeration</span></span>

<span data-ttu-id="395da-103">Enthält Werte, die das Verhalten des verwalteten JIT-Compilers (Just-In-Time) beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="395da-103">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="395da-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="395da-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="395da-105">Member</span><span class="sxs-lookup"><span data-stu-id="395da-105">Members</span></span>  
  
|<span data-ttu-id="395da-106">Member</span><span class="sxs-lookup"><span data-stu-id="395da-106">Member</span></span>|<span data-ttu-id="395da-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="395da-107">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|<span data-ttu-id="395da-108">Gibt an, dass der Compiler Kompilierungs Daten nachverfolgen und Optimierungen zulässt.</span><span class="sxs-lookup"><span data-stu-id="395da-108">Specifies that the compiler should track compilation data, and allows optimizations.</span></span>|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|<span data-ttu-id="395da-109">Gibt an, dass der Compiler Kompilierungs Daten nachverfolgen soll, aber Optimierungen deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="395da-109">Specifies that the compiler should track compilation data, but disables optimizations.</span></span>|  
|`CORDEBUG_JIT_ENABLE_ENC`|<span data-ttu-id="395da-110">Gibt an, dass der Compiler Kompilierungs Daten nachverfolgen, Optimierungen deaktiviert und die Technologien "Bearbeiten" und "Fortfahren" aktiviert.</span><span class="sxs-lookup"><span data-stu-id="395da-110">Specifies that the compiler should track compilation data, disables optimizations, and enables Edit and Continue technologies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="395da-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="395da-111">Requirements</span></span>  

 <span data-ttu-id="395da-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="395da-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="395da-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="395da-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="395da-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="395da-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="395da-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="395da-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="395da-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="395da-116">See also</span></span>

- [<span data-ttu-id="395da-117">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="395da-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
