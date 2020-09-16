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
ms.openlocfilehash: b9d27c3e3cd42039aeefcb517ecc81eadeb5c183
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557423"
---
# <a name="ilcodekind-enumeration"></a><span data-ttu-id="316ea-102">ILCodeKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="316ea-102">ILCodeKind Enumeration</span></span>
<span data-ttu-id="316ea-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="316ea-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="316ea-104">Stellt Werte bereit, die angeben, ob der Debugger auf lokale Variablen oder Code, die in der Profiler-ReJIT-Instrumentation hinzugefügt wurden, zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="316ea-104">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="316ea-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="316ea-105">Syntax</span></span>  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="316ea-106">Member</span><span class="sxs-lookup"><span data-stu-id="316ea-106">Members</span></span>  
  
|<span data-ttu-id="316ea-107">Membername</span><span class="sxs-lookup"><span data-stu-id="316ea-107">Member name</span></span>|<span data-ttu-id="316ea-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="316ea-108">Description</span></span>|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|<span data-ttu-id="316ea-109">Der Debugger hat keinen Zugriff auf Informationen aus der ReJIT-Instrumentierung.</span><span class="sxs-lookup"><span data-stu-id="316ea-109">The debugger does not have access to information from ReJIT instrumentation.</span></span>|  
|`ILCODE_REJIT_IL`|<span data-ttu-id="316ea-110">Der Debugger hat Zugriff auf Informationen aus der ReJIT-Instrumentierung.</span><span class="sxs-lookup"><span data-stu-id="316ea-110">The debugger has access to information from ReJIT instrumentation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="316ea-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="316ea-111">Remarks</span></span>  
 <span data-ttu-id="316ea-112">Ein Member der `ILCodeKind` -Enumeration kann an die Methoden [enumeratelocalvariablesex](icordebugilframe4-enumeratelocalvariablesex-method.md) und [getlocalvariableex](icordebugilframe4-getlocalvariableex-method.md) weitergegeben werden, um zu bestimmen, ob der Debugger auf Variablen zugreifen kann, die in der Profiler-ReJIT-Instrumentierung hinzugefügt wurden, und auf die [getcodeex](icordebugilframe4-getcodeex-method.md) -Methode, um zu bestimmen, ob der Debugger auf instrumentierte Il</span><span class="sxs-lookup"><span data-stu-id="316ea-112">A member of the `ILCodeKind` enumeration can be passed to the [EnumerateLocalVariablesEx](icordebugilframe4-enumeratelocalvariablesex-method.md) and [GetLocalVariableEx](icordebugilframe4-getlocalvariableex-method.md) methods to determine whether the debugger can access variables added in profiler ReJIT instrumentation, and to the [GetCodeEx](icordebugilframe4-getcodeex-method.md) method to determine whether the debugger can access instrumented IL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="316ea-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="316ea-113">Requirements</span></span>  
 <span data-ttu-id="316ea-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="316ea-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="316ea-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="316ea-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="316ea-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="316ea-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="316ea-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="316ea-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="316ea-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="316ea-118">See also</span></span>

- [<span data-ttu-id="316ea-119">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="316ea-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="316ea-120">ICorDebugILFrame4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="316ea-120">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="316ea-121">ReJIT: Anleitung</span><span class="sxs-lookup"><span data-stu-id="316ea-121">ReJIT: A How-To Guide</span></span>](/archive/blogs/davbr/rejit-a-how-to-guide)
