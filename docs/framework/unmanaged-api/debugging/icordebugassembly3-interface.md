---
title: ICorDebugAssembly3-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e581b4256da2ecc19a8b97520e0e70fef972b549
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="e163b-102">ICorDebugAssembly3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e163b-102">ICorDebugAssembly3 Interface</span></span>
<span data-ttu-id="e163b-103">Erweitert logisch die ICorDebugAssembly-Schnittstelle, um Container Assemblys und der darin enthaltenen Assemblys unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e163b-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e163b-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e163b-104">Methods</span></span>  
  
|<span data-ttu-id="e163b-105">Methode</span><span class="sxs-lookup"><span data-stu-id="e163b-105">Method</span></span>|<span data-ttu-id="e163b-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e163b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e163b-107">EnumerateContainedAssemblies-Methode</span><span class="sxs-lookup"><span data-stu-id="e163b-107">EnumerateContainedAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="e163b-108">Ruft einen Enumerator für die Assemblys ab, die in dieser Assembly enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="e163b-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="e163b-109">GetContainerAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="e163b-109">GetContainerAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="e163b-110">Gibt die Container-Assembly dieses `ICorDebugAssembly3`-Objekts aus.</span><span class="sxs-lookup"><span data-stu-id="e163b-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e163b-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e163b-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e163b-112">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e163b-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="e163b-113">Bei dem Versuch, `QueryInterface` aufzurufen, um einen Schnittstellenzeiger abzurufen, wird für ICorDebug-Szenarien außerhalb von .NET Native `E_NOINTERFACE` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e163b-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e163b-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e163b-114">Requirements</span></span>  
 <span data-ttu-id="e163b-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e163b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e163b-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e163b-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e163b-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e163b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e163b-118">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e163b-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e163b-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e163b-119">See Also</span></span>  
 [<span data-ttu-id="e163b-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e163b-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="e163b-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="e163b-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
