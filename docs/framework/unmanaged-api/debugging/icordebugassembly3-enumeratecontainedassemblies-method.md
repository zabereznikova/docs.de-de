---
title: ICorDebugAssembly3::EnumerateContainedAssemblies-Methode
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb84efe78568bbae03f76efc456fc8ae605e4db9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404835"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a><span data-ttu-id="280b1-102">ICorDebugAssembly3::EnumerateContainedAssemblies-Methode</span><span class="sxs-lookup"><span data-stu-id="280b1-102">ICorDebugAssembly3::EnumerateContainedAssemblies Method</span></span>
<span data-ttu-id="280b1-103">Ruft einen Enumerator für die Assemblys ab, die in dieser Assembly enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="280b1-103">Gets an enumerator for the assemblies contained in this assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="280b1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="280b1-104">Syntax</span></span>  
  
```  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="280b1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="280b1-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="280b1-106">[out] Ein Zeiger auf die Adresse eines ICorDebugAssemblyEnum-Schnittstelle-Objekts, das den Enumerator darstellt.</span><span class="sxs-lookup"><span data-stu-id="280b1-106">[out] A pointer to the address of an ICorDebugAssemblyEnum interface object that is the enumerator.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="280b1-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="280b1-107">Return Value</span></span>  
 <span data-ttu-id="280b1-108">`S_OK`, falls dieses `ICorDebugAssembly3`-Objekt ein Container ist; andernfalls `S_FALSE`, und die Enumeration ist leer.</span><span class="sxs-lookup"><span data-stu-id="280b1-108">`S_OK` if this `ICorDebugAssembly3` object is a container; otherwise, `S_FALSE`, and the enumeration is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="280b1-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="280b1-109">Remarks</span></span>  
 <span data-ttu-id="280b1-110">Symbole sind erforderlich, um die darin enthaltenen Assemblys aufzuführen.</span><span class="sxs-lookup"><span data-stu-id="280b1-110">Symbols are needed to enumerate the contained assemblies.</span></span> <span data-ttu-id="280b1-111">Wenn sie nicht vorhanden sind, gibt die Methode `S_FALSE` aus, und es wird kein gültiger Enumerator bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="280b1-111">If they aren't present, the method returns `S_FALSE`, and no valid enumerator is provided.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="280b1-112">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="280b1-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="280b1-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="280b1-113">Requirements</span></span>  
 <span data-ttu-id="280b1-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="280b1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="280b1-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="280b1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="280b1-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="280b1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="280b1-117">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="280b1-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="280b1-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="280b1-118">See Also</span></span>  
 [<span data-ttu-id="280b1-119">ICorDebugAssembly3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="280b1-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)  
 [<span data-ttu-id="280b1-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="280b1-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
