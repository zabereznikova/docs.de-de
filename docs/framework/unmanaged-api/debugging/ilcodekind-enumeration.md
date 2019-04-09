---
title: ILCodeKind-Enumeration
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ILCodeKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b91765e4-82db-46f9-a6dc-6b80610276af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f7e20618180961ab6d8ad0bbb79a626a4a7f4f7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145417"
---
# <a name="ilcodekind-enumeration"></a><span data-ttu-id="8c2d4-102">ILCodeKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="8c2d4-102">ILCodeKind Enumeration</span></span>
<span data-ttu-id="8c2d4-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="8c2d4-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="8c2d4-104">Stellt Werte bereit, die angeben, ob der Debugger auf lokale Variablen oder Code, die in der Profiler-ReJIT-Instrumentation hinzugefügt wurden, zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="8c2d4-104">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c2d4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8c2d4-105">Syntax</span></span>  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="8c2d4-106">Member</span><span class="sxs-lookup"><span data-stu-id="8c2d4-106">Members</span></span>  
  
|<span data-ttu-id="8c2d4-107">Membername</span><span class="sxs-lookup"><span data-stu-id="8c2d4-107">Member name</span></span>|<span data-ttu-id="8c2d4-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8c2d4-108">Description</span></span>|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|<span data-ttu-id="8c2d4-109">Der Debugger hat keinen Zugriff auf Informationen aus der ReJIT-Instrumentierung.</span><span class="sxs-lookup"><span data-stu-id="8c2d4-109">The debugger does not have access to information from ReJIT instrumentation.</span></span>|  
|`ILCODE_REJIT_IL`|<span data-ttu-id="8c2d4-110">Der Debugger hat Zugriff auf Informationen aus der ReJIT-Instrumentierung.</span><span class="sxs-lookup"><span data-stu-id="8c2d4-110">The debugger has access to information from ReJIT instrumentation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c2d4-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8c2d4-111">Remarks</span></span>  
 <span data-ttu-id="8c2d4-112">Ein Mitglied der `ILCodeKind` Enumeration übergeben werden kann, um die [EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) und [GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) Methoden, um zu bestimmen, ob der Debugger in der Profiler-hinzugefügte Variablen zugreifen kann ReJIT-Instrumentierung, und die [GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) IL instrumentiert, Methode, um zu bestimmen, ob der Debugger zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="8c2d4-112">A member of the `ILCodeKind` enumeration can be passed to the [EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) and [GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) methods to determine whether the debugger can access variables added in profiler ReJIT instrumentation, and to the [GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) method to determine whether the debugger can access instrumented IL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c2d4-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8c2d4-113">Requirements</span></span>  
 <span data-ttu-id="8c2d4-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c2d4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c2d4-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c2d4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c2d4-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c2d4-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="8c2d4-117">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="8c2d4-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8c2d4-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c2d4-118">See also</span></span>

- [<span data-ttu-id="8c2d4-119">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="8c2d4-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="8c2d4-120">ICorDebugILFrame4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8c2d4-120">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [<span data-ttu-id="8c2d4-121">ReJIT: Einen Leitfaden zur Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="8c2d4-121">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
