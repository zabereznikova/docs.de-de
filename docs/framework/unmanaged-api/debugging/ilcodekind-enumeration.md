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
ms.openlocfilehash: 20e2e3f177b12221832786f4fab86635098d1989
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790488"
---
# <a name="ilcodekind-enumeration"></a><span data-ttu-id="30e05-102">ILCodeKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="30e05-102">ILCodeKind Enumeration</span></span>
<span data-ttu-id="30e05-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="30e05-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="30e05-104">Stellt Werte bereit, die angeben, ob der Debugger auf lokale Variablen oder Code, die in der Profiler-ReJIT-Instrumentation hinzugefügt wurden, zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="30e05-104">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30e05-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="30e05-105">Syntax</span></span>  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="30e05-106">Member</span><span class="sxs-lookup"><span data-stu-id="30e05-106">Members</span></span>  
  
|<span data-ttu-id="30e05-107">Mitgliedsname</span><span class="sxs-lookup"><span data-stu-id="30e05-107">Member name</span></span>|<span data-ttu-id="30e05-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="30e05-108">Description</span></span>|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|<span data-ttu-id="30e05-109">Der Debugger hat keinen Zugriff auf Informationen aus der ReJIT-Instrumentierung.</span><span class="sxs-lookup"><span data-stu-id="30e05-109">The debugger does not have access to information from ReJIT instrumentation.</span></span>|  
|`ILCODE_REJIT_IL`|<span data-ttu-id="30e05-110">Der Debugger hat Zugriff auf Informationen aus der ReJIT-Instrumentierung.</span><span class="sxs-lookup"><span data-stu-id="30e05-110">The debugger has access to information from ReJIT instrumentation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30e05-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="30e05-111">Remarks</span></span>  
 <span data-ttu-id="30e05-112">Ein Member der `ILCodeKind` Enumeration kann an die Methoden [enumeratelocalvariablesex](icordebugilframe4-enumeratelocalvariablesex-method.md) und [getlocalvariableex](icordebugilframe4-getlocalvariableex-method.md) weitergegeben werden, um zu bestimmen, ob der Debugger auf Variablen zugreifen kann, die in der Profiler-ReJIT-Instrumentierung hinzugefügt wurden, und auf die Methode [getcodeex](icordebugilframe4-getcodeex-method.md) , um zu bestimmen, ob der Debugger auf instrumentierte Il zugreifen kann</span><span class="sxs-lookup"><span data-stu-id="30e05-112">A member of the `ILCodeKind` enumeration can be passed to the [EnumerateLocalVariablesEx](icordebugilframe4-enumeratelocalvariablesex-method.md) and [GetLocalVariableEx](icordebugilframe4-getlocalvariableex-method.md) methods to determine whether the debugger can access variables added in profiler ReJIT instrumentation, and to the [GetCodeEx](icordebugilframe4-getcodeex-method.md) method to determine whether the debugger can access instrumented IL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30e05-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="30e05-113">Requirements</span></span>  
 <span data-ttu-id="30e05-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30e05-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30e05-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30e05-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30e05-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30e05-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30e05-117">**.NET Framework Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30e05-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30e05-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30e05-118">See also</span></span>

- [<span data-ttu-id="30e05-119">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="30e05-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="30e05-120">ICorDebugILFrame4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="30e05-120">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="30e05-121">ReJIT: Anleitung</span><span class="sxs-lookup"><span data-stu-id="30e05-121">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
