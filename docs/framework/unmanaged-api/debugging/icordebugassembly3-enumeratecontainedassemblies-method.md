---
title: ICorDebugAssembly3::EnumerateContainedAssemblies-Methode
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
ms.openlocfilehash: 616675f839e562227558ece440bdfdf497747572
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784562"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a><span data-ttu-id="26b63-102">ICorDebugAssembly3::EnumerateContainedAssemblies-Methode</span><span class="sxs-lookup"><span data-stu-id="26b63-102">ICorDebugAssembly3::EnumerateContainedAssemblies Method</span></span>
<span data-ttu-id="26b63-103">Ruft einen Enumerator für die Assemblys ab, die in dieser Assembly enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="26b63-103">Gets an enumerator for the assemblies contained in this assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26b63-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="26b63-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26b63-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="26b63-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="26b63-106">[out] Ein Zeiger auf die Adresse eines ICorDebugAssemblyEnum -Schnittstellenobjekts, das den Enumerator darstellt.</span><span class="sxs-lookup"><span data-stu-id="26b63-106">[out] A pointer to the address of an ICorDebugAssemblyEnum interface object that is the enumerator.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="26b63-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="26b63-107">Return Value</span></span>  
 <span data-ttu-id="26b63-108">`S_OK`, falls dieses `ICorDebugAssembly3`-Objekt ein Container ist; andernfalls `S_FALSE`, und die Enumeration ist leer.</span><span class="sxs-lookup"><span data-stu-id="26b63-108">`S_OK` if this `ICorDebugAssembly3` object is a container; otherwise, `S_FALSE`, and the enumeration is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26b63-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="26b63-109">Remarks</span></span>  
 <span data-ttu-id="26b63-110">Symbole sind erforderlich, um die darin enthaltenen Assemblys aufzuführen.</span><span class="sxs-lookup"><span data-stu-id="26b63-110">Symbols are needed to enumerate the contained assemblies.</span></span> <span data-ttu-id="26b63-111">Wenn sie nicht vorhanden sind, gibt die Methode `S_FALSE` aus, und es wird kein gültiger Enumerator bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="26b63-111">If they aren't present, the method returns `S_FALSE`, and no valid enumerator is provided.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="26b63-112">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="26b63-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26b63-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="26b63-113">Requirements</span></span>  
 <span data-ttu-id="26b63-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26b63-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26b63-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26b63-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26b63-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26b63-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26b63-117">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26b63-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26b63-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26b63-118">See also</span></span>

- [<span data-ttu-id="26b63-119">ICorDebugAssembly3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="26b63-119">ICorDebugAssembly3 Interface</span></span>](icordebugassembly3-interface.md)
- [<span data-ttu-id="26b63-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="26b63-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
