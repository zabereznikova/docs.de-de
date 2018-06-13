---
title: ICorProfilerInfo7-Schnittstelle
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 79a722cd3318def36c20a49c1567c6f0d4989d39
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455405"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="1de62-102">ICorProfilerInfo7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1de62-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="1de62-103">[Unterstützt in [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] und höheren Versionen]</span><span class="sxs-lookup"><span data-stu-id="1de62-103">[Supported in the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="1de62-104">Eine Unterklasse von [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) , eine Methode, um neu anzuwenden Metadaten eines Moduls definiert und Zugriff auf ein in-Memory-symbolstream bereitstellt bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="1de62-104">A subclass of [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1de62-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="1de62-105">Methods</span></span>  
  
|<span data-ttu-id="1de62-106">Methode</span><span class="sxs-lookup"><span data-stu-id="1de62-106">Method</span></span>|<span data-ttu-id="1de62-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1de62-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1de62-108">ApplyMetaData-Methode</span><span class="sxs-lookup"><span data-stu-id="1de62-108">ApplyMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="1de62-109">Wendet die neu definierte von Metadaten der `IMetadataEmit::Define*` Methoden, um ein angegebenes Modul.</span><span class="sxs-lookup"><span data-stu-id="1de62-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="1de62-110">GetInMemorySymbolsLength-Methode</span><span class="sxs-lookup"><span data-stu-id="1de62-110">GetInMemorySymbolsLength Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="1de62-111">Gibt die Länge eines Datenstroms in-Memory-Symbols zurück.</span><span class="sxs-lookup"><span data-stu-id="1de62-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="1de62-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="1de62-112">ReadInMemorySymbols</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="1de62-113">Liest Bytes aus einem Datenstrom in-Memory-Symbol.</span><span class="sxs-lookup"><span data-stu-id="1de62-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1de62-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1de62-114">Requirements</span></span>  
 <span data-ttu-id="1de62-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1de62-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1de62-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1de62-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1de62-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1de62-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1de62-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1de62-118">See Also</span></span>  
 [<span data-ttu-id="1de62-119">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="1de62-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
