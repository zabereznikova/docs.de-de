---
title: ICorProfilerInfo7-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 13282bec74df5e6159148aa4fbe92a84d035e044
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="4f7b6-102">ICorProfilerInfo7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4f7b6-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="4f7b6-103">[Unterstützt in [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] und höheren Versionen]</span><span class="sxs-lookup"><span data-stu-id="4f7b6-103">[Supported in the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="4f7b6-104">Eine Unterklasse von [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) , eine Methode, um neu anzuwenden Metadaten eines Moduls definiert und Zugriff auf ein in-Memory-symbolstream bereitstellt bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="4f7b6-104">A subclass of [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4f7b6-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="4f7b6-105">Methods</span></span>  
  
|<span data-ttu-id="4f7b6-106">Methode</span><span class="sxs-lookup"><span data-stu-id="4f7b6-106">Method</span></span>|<span data-ttu-id="4f7b6-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4f7b6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4f7b6-108">ApplyMetaData-Methode</span><span class="sxs-lookup"><span data-stu-id="4f7b6-108">ApplyMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="4f7b6-109">Wendet die neu definierte von Metadaten der `IMetadataEmit::Define*` Methoden, um ein angegebenes Modul.</span><span class="sxs-lookup"><span data-stu-id="4f7b6-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="4f7b6-110">GetInMemorySymbolsLength-Methode</span><span class="sxs-lookup"><span data-stu-id="4f7b6-110">GetInMemorySymbolsLength Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="4f7b6-111">Gibt die Länge eines Datenstroms in-Memory-Symbols zurück.</span><span class="sxs-lookup"><span data-stu-id="4f7b6-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="4f7b6-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="4f7b6-112">ReadInMemorySymbols</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="4f7b6-113">Liest Bytes aus einem Datenstrom in-Memory-Symbol.</span><span class="sxs-lookup"><span data-stu-id="4f7b6-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4f7b6-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4f7b6-114">Requirements</span></span>  
 <span data-ttu-id="4f7b6-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f7b6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f7b6-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4f7b6-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4f7b6-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f7b6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f7b6-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f7b6-118">See Also</span></span>  
 [<span data-ttu-id="4f7b6-119">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="4f7b6-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
