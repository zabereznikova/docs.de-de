---
title: ICorDebugSymbolProvider2-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7666b8d64b689d3640594f07614be97b72e85a8f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="f0e7c-102">ICorDebugSymbolProvider2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f0e7c-102">ICorDebugSymbolProvider2 Interface</span></span>
<span data-ttu-id="f0e7c-103">Erweitert logisch die [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) Schnittstelle, um zusätzliche Debugsymbolinformationen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f0e7c-103">Logically extends the [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f0e7c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f0e7c-104">Methods</span></span>  
  
|<span data-ttu-id="f0e7c-105">Methode</span><span class="sxs-lookup"><span data-stu-id="f0e7c-105">Method</span></span>|<span data-ttu-id="f0e7c-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0e7c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f0e7c-107">GetFrameProps-Methode</span><span class="sxs-lookup"><span data-stu-id="f0e7c-107">GetFrameProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="f0e7c-108">Gibt die relative virtuelle Startadresse einer Methode und den übergeordneten Frame zurück, wenn eine coderelative virtuelle Adresse angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f0e7c-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="f0e7c-109">GetGenericDictionaryInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="f0e7c-109">GetGenericDictionaryInfo Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="f0e7c-110">Ruft eine generische Wörterbuchzuordnung ab.</span><span class="sxs-lookup"><span data-stu-id="f0e7c-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0e7c-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f0e7c-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0e7c-112">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f0e7c-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="f0e7c-113">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="f0e7c-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0e7c-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f0e7c-114">Requirements</span></span>  
 <span data-ttu-id="f0e7c-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0e7c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0e7c-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0e7c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0e7c-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0e7c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0e7c-118">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0e7c-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0e7c-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0e7c-119">See Also</span></span>  
 [<span data-ttu-id="f0e7c-120">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f0e7c-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="f0e7c-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f0e7c-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="f0e7c-122">Debuggen</span><span class="sxs-lookup"><span data-stu-id="f0e7c-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
