---
title: CorDebugJITCompilerFlagsDeprecated-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugJITCompilerFlagsDeprecated
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugJITCompilerFlagsDeprecated
helpviewer_keywords:
- CorDebugJITCompilerFlagsDeprecated enumeration [.NET Framework debugging]
ms.assetid: af15e2ca-6be1-472b-bd36-03644a1e3ddd
topic_type:
- apiref
ms.openlocfilehash: 39b90ba35510a5eda7b34e0a80b0e889e5804ca7
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778228"
---
# <a name="cordebugjitcompilerflagsdeprecated-enumeration"></a><span data-ttu-id="e79b8-102">CorDebugJITCompilerFlagsDeprecated-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e79b8-102">CorDebugJITCompilerFlagsDeprecated Enumeration</span></span>
<span data-ttu-id="e79b8-103">Diese Enumeration ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="e79b8-103">This enumeration is obsolete.</span></span> <span data-ttu-id="e79b8-104">Verwenden Sie stattdessen den `CORDEBUG_JIT_DEFAULT` Member der [Cordebug-Compilerflags](cordebugjitcompilerflags-enumeration.md) -Enumeration.</span><span class="sxs-lookup"><span data-stu-id="e79b8-104">Use the `CORDEBUG_JIT_DEFAULT` member of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e79b8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e79b8-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugJITCompilerFlagsDeprecated {  
    CORDEBUG_JIT_TRACK_DEBUG_INFO  = 0x1  
} CorDebugJITCompilerFlagsDeprecated;  
```  
  
## <a name="members"></a><span data-ttu-id="e79b8-106">Member</span><span class="sxs-lookup"><span data-stu-id="e79b8-106">Members</span></span>  
  
|<span data-ttu-id="e79b8-107">Member</span><span class="sxs-lookup"><span data-stu-id="e79b8-107">Member</span></span>|<span data-ttu-id="e79b8-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e79b8-108">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_TRACK_DEBUG_INFO`|<span data-ttu-id="e79b8-109">Verwenden Sie stattdessen `CORDEBUG_JIT_DEFAULT` .</span><span class="sxs-lookup"><span data-stu-id="e79b8-109">Use `CORDEBUG_JIT_DEFAULT` instead.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e79b8-110">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e79b8-110">Requirements</span></span>  
 <span data-ttu-id="e79b8-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e79b8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e79b8-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e79b8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e79b8-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e79b8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e79b8-114">**.NET Framework Versionen:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="e79b8-114">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e79b8-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e79b8-115">See also</span></span>

- [<span data-ttu-id="e79b8-116">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="e79b8-116">Debugging Enumerations</span></span>](debugging-enumerations.md)
