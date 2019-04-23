---
title: ICLRDataEnumMemoryRegionsCallback-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback
helpviewer_keywords:
- ICLRDataEnumMemoryRegionsCallback interface [.NET Framework debugging]
ms.assetid: 3f1af8b0-8478-48e0-a7ec-3e90e0b97649
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dad66c8a55982762ede754a4b3cd747b7a91b87d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59225429"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="7b475-102">ICLRDataEnumMemoryRegionsCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b475-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="7b475-103">Stellt eine Rückrufmethode für [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) zum Berichten an den Debugger des Ergebnis der Versuch, einen angegebenen Speicherbereich aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="7b475-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7b475-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="7b475-104">Methods</span></span>  
  
|<span data-ttu-id="7b475-105">Methode</span><span class="sxs-lookup"><span data-stu-id="7b475-105">Method</span></span>|<span data-ttu-id="7b475-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b475-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7b475-107">EnumMemoryRegion-Methode</span><span class="sxs-lookup"><span data-stu-id="7b475-107">EnumMemoryRegion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="7b475-108">Wird aufgerufen, indem `ICLRDataEnumMemoryRegions::EnumMemoryRegions` zum Berichten an den Debugger des Ergebnis der Versuch, einen angegebenen Speicherbereich aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="7b475-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7b475-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7b475-109">Requirements</span></span>  
 <span data-ttu-id="7b475-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b475-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b475-111">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="7b475-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="7b475-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b475-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b475-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b475-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b475-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b475-114">See also</span></span>

- [<span data-ttu-id="7b475-115">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7b475-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
