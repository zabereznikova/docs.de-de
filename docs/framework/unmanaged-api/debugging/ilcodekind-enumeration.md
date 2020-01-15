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
ms.openlocfilehash: 553a92812f009ca1033f1bdcda0ea3722c5f01e3
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937838"
---
# <a name="ilcodekind-enumeration"></a><span data-ttu-id="b8a97-102">ILCodeKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b8a97-102">ILCodeKind Enumeration</span></span>
<span data-ttu-id="b8a97-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="b8a97-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="b8a97-104">Stellt Werte bereit, die angeben, ob der Debugger auf lokale Variablen oder Code, die in der Profiler-ReJIT-Instrumentation hinzugefügt wurden, zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="b8a97-104">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8a97-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8a97-105">Syntax</span></span>  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="b8a97-106">Member</span><span class="sxs-lookup"><span data-stu-id="b8a97-106">Members</span></span>  
  
|<span data-ttu-id="b8a97-107">Mitgliedsname</span><span class="sxs-lookup"><span data-stu-id="b8a97-107">Member name</span></span>|<span data-ttu-id="b8a97-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b8a97-108">Description</span></span>|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|<span data-ttu-id="b8a97-109">Der Debugger hat keinen Zugriff auf Informationen aus der ReJIT-Instrumentierung.</span><span class="sxs-lookup"><span data-stu-id="b8a97-109">The debugger does not have access to information from ReJIT instrumentation.</span></span>|  
|`ILCODE_REJIT_IL`|<span data-ttu-id="b8a97-110">Der Debugger hat Zugriff auf Informationen aus der ReJIT-Instrumentierung.</span><span class="sxs-lookup"><span data-stu-id="b8a97-110">The debugger has access to information from ReJIT instrumentation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8a97-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b8a97-111">Remarks</span></span>  
 <span data-ttu-id="b8a97-112">Ein Member der `ILCodeKind` Enumeration kann an die Methoden [enumeratelocalvariablesex](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) und [getlocalvariableex](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) weitergegeben werden, um zu bestimmen, ob der Debugger auf Variablen zugreifen kann, die in der Profiler-ReJIT-Instrumentierung hinzugefügt wurden, und auf die Methode [getcodeex](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) , um zu bestimmen, ob der Debugger auf instrumentierte Il zugreifen kann</span><span class="sxs-lookup"><span data-stu-id="b8a97-112">A member of the `ILCodeKind` enumeration can be passed to the [EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) and [GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) methods to determine whether the debugger can access variables added in profiler ReJIT instrumentation, and to the [GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) method to determine whether the debugger can access instrumented IL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8a97-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b8a97-113">Requirements</span></span>  
 <span data-ttu-id="b8a97-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8a97-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8a97-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b8a97-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8a97-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8a97-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8a97-117">**.NET Framework Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8a97-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8a97-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8a97-118">See also</span></span>

- [<span data-ttu-id="b8a97-119">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="b8a97-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="b8a97-120">ICorDebugILFrame4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8a97-120">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [<span data-ttu-id="b8a97-121">ReJIT: Anleitung</span><span class="sxs-lookup"><span data-stu-id="b8a97-121">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
