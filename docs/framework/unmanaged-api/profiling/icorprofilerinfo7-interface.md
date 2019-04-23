---
title: ICorProfilerInfo7-Schnittstelle
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d8586031c5bcb0303a64b67ee601fe41b81ee3f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59134852"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="e75c4-102">ICorProfilerInfo7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e75c4-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="e75c4-103">[Unterstützt in [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] und höheren Versionen]</span><span class="sxs-lookup"><span data-stu-id="e75c4-103">[Supported in the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="e75c4-104">Eine Unterklasse von [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) , bereitstellt, eine Methode, um neu anwenden Metadaten zu einem Modul definiert und Zugriff auf eine in-Memory symbolstream bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="e75c4-104">A subclass of [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e75c4-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="e75c4-105">Methods</span></span>  
  
|<span data-ttu-id="e75c4-106">Methode</span><span class="sxs-lookup"><span data-stu-id="e75c4-106">Method</span></span>|<span data-ttu-id="e75c4-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e75c4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e75c4-108">ApplyMetaData-Methode</span><span class="sxs-lookup"><span data-stu-id="e75c4-108">ApplyMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="e75c4-109">Wendet die Metadaten von neu definiert die `IMetadataEmit::Define*` Methoden für ein angegebenes Modul.</span><span class="sxs-lookup"><span data-stu-id="e75c4-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="e75c4-110">GetInMemorySymbolsLength-Methode</span><span class="sxs-lookup"><span data-stu-id="e75c4-110">GetInMemorySymbolsLength Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="e75c4-111">Gibt die Länge einer in-Memory symbolstream zurück.</span><span class="sxs-lookup"><span data-stu-id="e75c4-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="e75c4-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="e75c4-112">ReadInMemorySymbols</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="e75c4-113">Liest Bytes aus einem in-Memory symbolstream.</span><span class="sxs-lookup"><span data-stu-id="e75c4-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e75c4-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e75c4-114">Requirements</span></span>  
 <span data-ttu-id="e75c4-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e75c4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e75c4-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e75c4-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e75c4-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e75c4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e75c4-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e75c4-118">See also</span></span>

- [<span data-ttu-id="e75c4-119">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e75c4-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
