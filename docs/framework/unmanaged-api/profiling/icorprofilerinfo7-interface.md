---
title: ICorProfilerInfo7-Schnittstelle
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
ms.openlocfilehash: f80f310c10bae33583cb7cd2048ede4f5efbe14c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861748"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="f376b-102">ICorProfilerInfo7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f376b-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="f376b-103">[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="f376b-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="f376b-104">Eine Unterklasse von [ICorProfilerInfo6](icorprofilerinfo6-interface.md) , die eine Methode bereitstellt, mit der neu definierte Metadaten auf ein Modul angewendet werden können und der Zugriff auf einen in-Memory-symbolstream bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f376b-104">A subclass of [ICorProfilerInfo6](icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f376b-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="f376b-105">Methods</span></span>  
  
|<span data-ttu-id="f376b-106">-Methode</span><span class="sxs-lookup"><span data-stu-id="f376b-106">Method</span></span>|<span data-ttu-id="f376b-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f376b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f376b-108">ApplyMetaData-Methode</span><span class="sxs-lookup"><span data-stu-id="f376b-108">ApplyMetaData Method</span></span>](icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="f376b-109">Wendet die durch die `IMetadataEmit::Define*`-Methoden neu definierten Metadaten auf ein angegebenes Modul an.</span><span class="sxs-lookup"><span data-stu-id="f376b-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="f376b-110">GetInMemorySymbolsLength-Methode</span><span class="sxs-lookup"><span data-stu-id="f376b-110">GetInMemorySymbolsLength Method</span></span>](icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="f376b-111">Gibt die Länge eines in-Memory-Symbol Datenstroms zurück.</span><span class="sxs-lookup"><span data-stu-id="f376b-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="f376b-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="f376b-112">ReadInMemorySymbols</span></span>](icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="f376b-113">Liest Bytes aus einem in-Memory-symbolstream.</span><span class="sxs-lookup"><span data-stu-id="f376b-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f376b-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f376b-114">Requirements</span></span>  
 <span data-ttu-id="f376b-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f376b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f376b-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f376b-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f376b-117">**.NET Framework Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f376b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f376b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f376b-118">See also</span></span>

- [<span data-ttu-id="f376b-119">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f376b-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
