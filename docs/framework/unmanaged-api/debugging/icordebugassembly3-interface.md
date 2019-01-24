---
title: ICorDebugAssembly3-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 66d3024c0bb2c0014cbec2b24deb7b0d5845fe88
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627524"
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="9b41a-102">ICorDebugAssembly3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b41a-102">ICorDebugAssembly3 Interface</span></span>
<span data-ttu-id="9b41a-103">Erweitert logisch die ICorDebugAssembly-Schnittstelle, um die Container-Assemblys und der darin enthaltenen Assemblys unterstützen.</span><span class="sxs-lookup"><span data-stu-id="9b41a-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9b41a-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="9b41a-104">Methods</span></span>  
  
|<span data-ttu-id="9b41a-105">Methode</span><span class="sxs-lookup"><span data-stu-id="9b41a-105">Method</span></span>|<span data-ttu-id="9b41a-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b41a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9b41a-107">EnumerateContainedAssemblies-Methode</span><span class="sxs-lookup"><span data-stu-id="9b41a-107">EnumerateContainedAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="9b41a-108">Ruft einen Enumerator für die Assemblys ab, die in dieser Assembly enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="9b41a-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="9b41a-109">GetContainerAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="9b41a-109">GetContainerAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="9b41a-110">Gibt die Container-Assembly dieses `ICorDebugAssembly3`-Objekts aus.</span><span class="sxs-lookup"><span data-stu-id="9b41a-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b41a-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9b41a-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b41a-112">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9b41a-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="9b41a-113">Bei dem Versuch, `QueryInterface` aufzurufen, um einen Schnittstellenzeiger abzurufen, wird für ICorDebug-Szenarien außerhalb von .NET Native `E_NOINTERFACE` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9b41a-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b41a-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9b41a-114">Requirements</span></span>  
 <span data-ttu-id="9b41a-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b41a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b41a-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b41a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b41a-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b41a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b41a-118">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b41a-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b41a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b41a-119">See also</span></span>
- [<span data-ttu-id="9b41a-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9b41a-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="9b41a-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="9b41a-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
