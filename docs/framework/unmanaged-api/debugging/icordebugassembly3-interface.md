---
title: ICorDebugAssembly3-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
ms.openlocfilehash: 0260267a05a880fbb3ac48325e55deff326f5f87
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688366"
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="c069b-102">ICorDebugAssembly3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c069b-102">ICorDebugAssembly3 Interface</span></span>

<span data-ttu-id="c069b-103">Erweitert logisch die ICorDebugAssembly-Schnittstelle zur Unterstützung der Container Assemblys und der darin enthaltenen Assemblys.</span><span class="sxs-lookup"><span data-stu-id="c069b-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c069b-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="c069b-104">Methods</span></span>  
  
|<span data-ttu-id="c069b-105">Methode</span><span class="sxs-lookup"><span data-stu-id="c069b-105">Method</span></span>|<span data-ttu-id="c069b-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c069b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c069b-107">EnumerateContainedAssemblies-Methode</span><span class="sxs-lookup"><span data-stu-id="c069b-107">EnumerateContainedAssemblies Method</span></span>](icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="c069b-108">Ruft einen Enumerator für die Assemblys ab, die in dieser Assembly enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="c069b-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="c069b-109">GetContainerAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="c069b-109">GetContainerAssembly Method</span></span>](icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="c069b-110">Gibt die Container-Assembly dieses `ICorDebugAssembly3`-Objekts aus.</span><span class="sxs-lookup"><span data-stu-id="c069b-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c069b-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c069b-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c069b-112">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c069b-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="c069b-113">Bei dem Versuch, `QueryInterface` aufzurufen, um einen Schnittstellenzeiger abzurufen, wird für ICorDebug-Szenarien außerhalb von .NET Native `E_NOINTERFACE` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c069b-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c069b-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c069b-114">Requirements</span></span>  

 <span data-ttu-id="c069b-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c069b-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c069b-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c069b-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c069b-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c069b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c069b-118">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c069b-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c069b-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c069b-119">See also</span></span>

- [<span data-ttu-id="c069b-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c069b-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c069b-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="c069b-121">Debugging</span></span>](index.md)
