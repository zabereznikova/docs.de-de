---
title: ICorProfilerInfo7-Schnittstelle
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a734bfdef89d4f8f9459f49a3ce2cee83faef9f6
ms.sourcegitcommit: 26f4a7697c32978f6a328c89dc4ea87034065989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2019
ms.locfileid: "66250985"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="7ddd8-102">ICorProfilerInfo7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ddd8-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="7ddd8-103">[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="7ddd8-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="7ddd8-104">Eine Unterklasse von [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) , bereitstellt, eine Methode, um neu anwenden Metadaten zu einem Modul definiert und Zugriff auf eine in-Memory symbolstream bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="7ddd8-104">A subclass of [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7ddd8-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="7ddd8-105">Methods</span></span>  
  
|<span data-ttu-id="7ddd8-106">Methode</span><span class="sxs-lookup"><span data-stu-id="7ddd8-106">Method</span></span>|<span data-ttu-id="7ddd8-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ddd8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7ddd8-108">ApplyMetaData-Methode</span><span class="sxs-lookup"><span data-stu-id="7ddd8-108">ApplyMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="7ddd8-109">Wendet die Metadaten von neu definiert die `IMetadataEmit::Define*` Methoden für ein angegebenes Modul.</span><span class="sxs-lookup"><span data-stu-id="7ddd8-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="7ddd8-110">GetInMemorySymbolsLength-Methode</span><span class="sxs-lookup"><span data-stu-id="7ddd8-110">GetInMemorySymbolsLength Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="7ddd8-111">Gibt die Länge einer in-Memory symbolstream zurück.</span><span class="sxs-lookup"><span data-stu-id="7ddd8-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="7ddd8-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="7ddd8-112">ReadInMemorySymbols</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="7ddd8-113">Liest Bytes aus einem in-Memory symbolstream.</span><span class="sxs-lookup"><span data-stu-id="7ddd8-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7ddd8-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7ddd8-114">Requirements</span></span>  
 <span data-ttu-id="7ddd8-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ddd8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ddd8-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7ddd8-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7ddd8-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ddd8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ddd8-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ddd8-118">See also</span></span>

- [<span data-ttu-id="7ddd8-119">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="7ddd8-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
