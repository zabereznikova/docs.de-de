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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698186"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="b84a1-102">ICLRDataEnumMemoryRegionsCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b84a1-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="b84a1-103">Stellt eine Rückrufmethode für [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) zum Berichten an den Debugger des Ergebnis der Versuch, einen angegebenen Speicherbereich aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="b84a1-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b84a1-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="b84a1-104">Methods</span></span>  
  
|<span data-ttu-id="b84a1-105">Methode</span><span class="sxs-lookup"><span data-stu-id="b84a1-105">Method</span></span>|<span data-ttu-id="b84a1-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b84a1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b84a1-107">EnumMemoryRegion-Methode</span><span class="sxs-lookup"><span data-stu-id="b84a1-107">EnumMemoryRegion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="b84a1-108">Wird aufgerufen, indem `ICLRDataEnumMemoryRegions::EnumMemoryRegions` zum Berichten an den Debugger des Ergebnis der Versuch, einen angegebenen Speicherbereich aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="b84a1-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b84a1-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b84a1-109">Requirements</span></span>  
 <span data-ttu-id="b84a1-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b84a1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b84a1-111">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="b84a1-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="b84a1-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b84a1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b84a1-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b84a1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b84a1-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b84a1-114">See also</span></span>

- [<span data-ttu-id="b84a1-115">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b84a1-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
