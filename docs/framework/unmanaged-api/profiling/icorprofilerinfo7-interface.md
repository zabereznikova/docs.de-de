---
title: ICorProfilerInfo7-Schnittstelle
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d8586031c5bcb0303a64b67ee601fe41b81ee3f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786242"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="da154-102">ICorProfilerInfo7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="da154-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="da154-103">[Unterstützt in [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] und höheren Versionen]</span><span class="sxs-lookup"><span data-stu-id="da154-103">[Supported in the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="da154-104">Eine Unterklasse von [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) , bereitstellt, eine Methode, um neu anwenden Metadaten zu einem Modul definiert und Zugriff auf eine in-Memory symbolstream bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="da154-104">A subclass of [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="da154-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="da154-105">Methods</span></span>  
  
|<span data-ttu-id="da154-106">Methode</span><span class="sxs-lookup"><span data-stu-id="da154-106">Method</span></span>|<span data-ttu-id="da154-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="da154-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="da154-108">ApplyMetaData-Methode</span><span class="sxs-lookup"><span data-stu-id="da154-108">ApplyMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="da154-109">Wendet die Metadaten von neu definiert die `IMetadataEmit::Define*` Methoden für ein angegebenes Modul.</span><span class="sxs-lookup"><span data-stu-id="da154-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="da154-110">GetInMemorySymbolsLength-Methode</span><span class="sxs-lookup"><span data-stu-id="da154-110">GetInMemorySymbolsLength Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="da154-111">Gibt die Länge einer in-Memory symbolstream zurück.</span><span class="sxs-lookup"><span data-stu-id="da154-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="da154-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="da154-112">ReadInMemorySymbols</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="da154-113">Liest Bytes aus einem in-Memory symbolstream.</span><span class="sxs-lookup"><span data-stu-id="da154-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="da154-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="da154-114">Requirements</span></span>  
 <span data-ttu-id="da154-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da154-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da154-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="da154-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="da154-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da154-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da154-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da154-118">See also</span></span>

- [<span data-ttu-id="da154-119">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="da154-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
