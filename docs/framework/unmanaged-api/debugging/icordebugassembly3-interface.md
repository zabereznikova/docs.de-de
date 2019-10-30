---
title: ICorDebugAssembly3-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
ms.openlocfilehash: 930101f6cd4ebb9215d6420f774b8e066c54a4f8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095363"
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="10545-102">ICorDebugAssembly3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="10545-102">ICorDebugAssembly3 Interface</span></span>
<span data-ttu-id="10545-103">Erweitert die ICorDebugAssembly-Schnittstelle logisch, um die Unterstützung für containerassemblys und ihre enthaltenen Assemblys</span><span class="sxs-lookup"><span data-stu-id="10545-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="10545-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="10545-104">Methods</span></span>  
  
|<span data-ttu-id="10545-105">Methode</span><span class="sxs-lookup"><span data-stu-id="10545-105">Method</span></span>|<span data-ttu-id="10545-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="10545-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="10545-107">EnumerateContainedAssemblies-Methode</span><span class="sxs-lookup"><span data-stu-id="10545-107">EnumerateContainedAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="10545-108">Ruft einen Enumerator für die Assemblys ab, die in dieser Assembly enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="10545-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="10545-109">GetContainerAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="10545-109">GetContainerAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="10545-110">Gibt die Container-Assembly dieses `ICorDebugAssembly3`-Objekts aus.</span><span class="sxs-lookup"><span data-stu-id="10545-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10545-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="10545-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="10545-112">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="10545-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="10545-113">Bei dem Versuch, `QueryInterface` aufzurufen, um einen Schnittstellenzeiger abzurufen, wird für ICorDebug-Szenarien außerhalb von .NET Native `E_NOINTERFACE` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="10545-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10545-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="10545-114">Requirements</span></span>  
 <span data-ttu-id="10545-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10545-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10545-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="10545-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10545-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10545-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10545-118">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10545-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10545-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10545-119">See also</span></span>

- [<span data-ttu-id="10545-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="10545-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="10545-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="10545-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
