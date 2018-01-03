---
title: ICorDebugAssembly3::EnumerateContainedAssemblies-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8633ce497cd282303c46692a942fe5f88be444c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a><span data-ttu-id="b7b10-102">ICorDebugAssembly3::EnumerateContainedAssemblies-Methode</span><span class="sxs-lookup"><span data-stu-id="b7b10-102">ICorDebugAssembly3::EnumerateContainedAssemblies Method</span></span>
<span data-ttu-id="b7b10-103">Ruft einen Enumerator für die Assemblys ab, die in dieser Assembly enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="b7b10-103">Gets an enumerator for the assemblies contained in this assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7b10-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b7b10-104">Syntax</span></span>  
  
```  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b7b10-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b7b10-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="b7b10-106">[out] Ein Zeiger auf die Adresse eines ICorDebugAssemblyEnum-Schnittstelle-Objekts, das den Enumerator darstellt.</span><span class="sxs-lookup"><span data-stu-id="b7b10-106">[out] A pointer to the address of an ICorDebugAssemblyEnum interface object that is the enumerator.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b7b10-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b7b10-107">Return Value</span></span>  
 <span data-ttu-id="b7b10-108">`S_OK`, falls dieses `ICorDebugAssembly3`-Objekt ein Container ist; andernfalls `S_FALSE`, und die Enumeration ist leer.</span><span class="sxs-lookup"><span data-stu-id="b7b10-108">`S_OK` if this `ICorDebugAssembly3` object is a container; otherwise, `S_FALSE`, and the enumeration is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7b10-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b7b10-109">Remarks</span></span>  
 <span data-ttu-id="b7b10-110">Symbole sind erforderlich, um die darin enthaltenen Assemblys aufzuführen.</span><span class="sxs-lookup"><span data-stu-id="b7b10-110">Symbols are needed to enumerate the contained assemblies.</span></span> <span data-ttu-id="b7b10-111">Wenn sie nicht vorhanden sind, gibt die Methode `S_FALSE` aus, und es wird kein gültiger Enumerator bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="b7b10-111">If they aren't present, the method returns `S_FALSE`, and no valid enumerator is provided.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7b10-112">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b7b10-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7b10-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b7b10-113">Requirements</span></span>  
 <span data-ttu-id="b7b10-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7b10-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7b10-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7b10-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7b10-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7b10-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7b10-117">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7b10-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7b10-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7b10-118">See Also</span></span>  
 [<span data-ttu-id="b7b10-119">ICorDebugAssembly3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b7b10-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)  
 [<span data-ttu-id="b7b10-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b7b10-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
