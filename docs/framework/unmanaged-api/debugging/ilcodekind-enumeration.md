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
ms.openlocfilehash: 0586b9e184a0958b978837601db002e035881cbc
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421032"
---
# <a name="ilcodekind-enumeration"></a><span data-ttu-id="89f9b-102">ILCodeKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="89f9b-102">ILCodeKind Enumeration</span></span>
<span data-ttu-id="89f9b-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="89f9b-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="89f9b-104">Stellt Werte bereit, die angeben, ob der Debugger auf lokale Variablen oder Code, die in der Profiler-ReJIT-Instrumentation hinzugefügt wurden, zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="89f9b-104">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89f9b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="89f9b-105">Syntax</span></span>  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="89f9b-106">Member</span><span class="sxs-lookup"><span data-stu-id="89f9b-106">Members</span></span>  
  
|<span data-ttu-id="89f9b-107">Membername</span><span class="sxs-lookup"><span data-stu-id="89f9b-107">Member name</span></span>|<span data-ttu-id="89f9b-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="89f9b-108">Description</span></span>|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|<span data-ttu-id="89f9b-109">Der Debugger hat keinen Zugriff auf Informationen aus der ReJIT-Instrumentierung.</span><span class="sxs-lookup"><span data-stu-id="89f9b-109">The debugger does not have access to information from ReJIT instrumentation.</span></span>|  
|`ILCODE_REJIT_IL`|<span data-ttu-id="89f9b-110">Der Debugger hat Zugriff auf Informationen aus der ReJIT-Instrumentierung.</span><span class="sxs-lookup"><span data-stu-id="89f9b-110">The debugger has access to information from ReJIT instrumentation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89f9b-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="89f9b-111">Remarks</span></span>  
 <span data-ttu-id="89f9b-112">Ein Member der `ILCodeKind` -Enumeration kann an die Methoden [enumeratelocalvariablesex](icordebugilframe4-enumeratelocalvariablesex-method.md) und [getlocalvariableex](icordebugilframe4-getlocalvariableex-method.md) weitergegeben werden, um zu bestimmen, ob der Debugger auf Variablen zugreifen kann, die in der Profiler-ReJIT-Instrumentierung hinzugefügt wurden, und auf die [getcodeex](icordebugilframe4-getcodeex-method.md) -Methode, um zu bestimmen, ob der Debugger auf instrumentierte Il</span><span class="sxs-lookup"><span data-stu-id="89f9b-112">A member of the `ILCodeKind` enumeration can be passed to the [EnumerateLocalVariablesEx](icordebugilframe4-enumeratelocalvariablesex-method.md) and [GetLocalVariableEx](icordebugilframe4-getlocalvariableex-method.md) methods to determine whether the debugger can access variables added in profiler ReJIT instrumentation, and to the [GetCodeEx](icordebugilframe4-getcodeex-method.md) method to determine whether the debugger can access instrumented IL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89f9b-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="89f9b-113">Requirements</span></span>  
 <span data-ttu-id="89f9b-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89f9b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89f9b-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="89f9b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89f9b-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89f9b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89f9b-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89f9b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89f9b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89f9b-118">See also</span></span>

- [<span data-ttu-id="89f9b-119">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="89f9b-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="89f9b-120">ICorDebugILFrame4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="89f9b-120">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="89f9b-121">ReJIT: Anleitung</span><span class="sxs-lookup"><span data-stu-id="89f9b-121">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
