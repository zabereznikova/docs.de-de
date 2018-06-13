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
ms.openlocfilehash: 0a0af0c86bc44a4968119e1afd2a84e17e941601
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405498"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="e6dda-102">ICLRDataEnumMemoryRegionsCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e6dda-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="e6dda-103">Stellt eine Rückrufmethode für [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) auf das Ergebnis der Versuch, einen angegebenen Speicherbereich aufzulisten, die im Debugger zu melden.</span><span class="sxs-lookup"><span data-stu-id="e6dda-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e6dda-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e6dda-104">Methods</span></span>  
  
|<span data-ttu-id="e6dda-105">Methode</span><span class="sxs-lookup"><span data-stu-id="e6dda-105">Method</span></span>|<span data-ttu-id="e6dda-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6dda-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e6dda-107">EnumMemoryRegion-Methode</span><span class="sxs-lookup"><span data-stu-id="e6dda-107">EnumMemoryRegion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="e6dda-108">Wird aufgerufen, indem Sie `ICLRDataEnumMemoryRegions::EnumMemoryRegions` auf das Ergebnis der Versuch, einen angegebenen Speicherbereich aufzulisten, die im Debugger zu melden.</span><span class="sxs-lookup"><span data-stu-id="e6dda-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e6dda-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e6dda-109">Requirements</span></span>  
 <span data-ttu-id="e6dda-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6dda-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6dda-111">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="e6dda-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="e6dda-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6dda-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6dda-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6dda-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6dda-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6dda-114">See Also</span></span>  
 [<span data-ttu-id="e6dda-115">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e6dda-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
