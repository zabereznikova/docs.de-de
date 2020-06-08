---
title: ICorProfilerInfo7-Schnittstelle
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
ms.openlocfilehash: 0e9f76717aeff27e863245faac241927e7495076
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495488"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="983fc-102">ICorProfilerInfo7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="983fc-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="983fc-103">[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="983fc-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="983fc-104">Eine Unterklasse von [ICorProfilerInfo6](icorprofilerinfo6-interface.md) , die eine Methode bereitstellt, mit der neu definierte Metadaten auf ein Modul angewendet werden können und der Zugriff auf einen in-Memory-symbolstream bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="983fc-104">A subclass of [ICorProfilerInfo6](icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="983fc-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="983fc-105">Methods</span></span>  
  
|<span data-ttu-id="983fc-106">Methode</span><span class="sxs-lookup"><span data-stu-id="983fc-106">Method</span></span>|<span data-ttu-id="983fc-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="983fc-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="983fc-108">ApplyMetaData-Methode</span><span class="sxs-lookup"><span data-stu-id="983fc-108">ApplyMetaData Method</span></span>](icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="983fc-109">Wendet die durch die-Methoden neu definierten Metadaten auf ein angegebenes `IMetadataEmit::Define*` Modul an.</span><span class="sxs-lookup"><span data-stu-id="983fc-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="983fc-110">GetInMemorySymbolsLength-Methode</span><span class="sxs-lookup"><span data-stu-id="983fc-110">GetInMemorySymbolsLength Method</span></span>](icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="983fc-111">Gibt die Länge eines in-Memory-Symbol Datenstroms zurück.</span><span class="sxs-lookup"><span data-stu-id="983fc-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="983fc-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="983fc-112">ReadInMemorySymbols</span></span>](icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="983fc-113">Liest Bytes aus einem in-Memory-symbolstream.</span><span class="sxs-lookup"><span data-stu-id="983fc-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="983fc-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="983fc-114">Requirements</span></span>  
 <span data-ttu-id="983fc-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="983fc-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="983fc-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="983fc-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="983fc-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="983fc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="983fc-118">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="983fc-118">See also</span></span>

- [<span data-ttu-id="983fc-119">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="983fc-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
