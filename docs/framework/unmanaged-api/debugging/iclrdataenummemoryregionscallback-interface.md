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
ms.openlocfilehash: cf46133095d1345ffbe0356d3ab486c11ae6dbd6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122911"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="36a1e-102">ICLRDataEnumMemoryRegionsCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="36a1e-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="36a1e-103">Stellt eine Rückruf Methode für [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) bereit, um dem Debugger das Ergebnis eines Versuchs zum Auflisten eines bestimmten Speicherbereichs zu melden.</span><span class="sxs-lookup"><span data-stu-id="36a1e-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="36a1e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="36a1e-104">Methods</span></span>  
  
|<span data-ttu-id="36a1e-105">Methode</span><span class="sxs-lookup"><span data-stu-id="36a1e-105">Method</span></span>|<span data-ttu-id="36a1e-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="36a1e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="36a1e-107">EnumMemoryRegion-Methode</span><span class="sxs-lookup"><span data-stu-id="36a1e-107">EnumMemoryRegion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="36a1e-108">Wird von `ICLRDataEnumMemoryRegions::EnumMemoryRegions` aufgerufen, um dem Debugger zu melden, das Ergebnis eines Versuchs, einen angegebenen Bereich des Speichers aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="36a1e-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="36a1e-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="36a1e-109">Requirements</span></span>  
 <span data-ttu-id="36a1e-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36a1e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36a1e-111">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="36a1e-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="36a1e-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36a1e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36a1e-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36a1e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36a1e-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36a1e-114">See also</span></span>

- [<span data-ttu-id="36a1e-115">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="36a1e-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
