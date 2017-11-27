---
title: ICLRDataEnumMemoryRegionsCallback-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataEnumMemoryRegionsCallback
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataEnumMemoryRegionsCallback
helpviewer_keywords: ICLRDataEnumMemoryRegionsCallback interface [.NET Framework debugging]
ms.assetid: 3f1af8b0-8478-48e0-a7ec-3e90e0b97649
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 40e51bfc176d8be6b008bc4274c0933253d7be3a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="1348c-102">ICLRDataEnumMemoryRegionsCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1348c-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="1348c-103">Stellt eine Rückrufmethode für [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) auf das Ergebnis der Versuch, einen angegebenen Speicherbereich aufzulisten, die im Debugger zu melden.</span><span class="sxs-lookup"><span data-stu-id="1348c-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1348c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="1348c-104">Methods</span></span>  
  
|<span data-ttu-id="1348c-105">Methode</span><span class="sxs-lookup"><span data-stu-id="1348c-105">Method</span></span>|<span data-ttu-id="1348c-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1348c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1348c-107">EnumMemoryRegion-Methode</span><span class="sxs-lookup"><span data-stu-id="1348c-107">EnumMemoryRegion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="1348c-108">Wird aufgerufen, indem Sie `ICLRDataEnumMemoryRegions::EnumMemoryRegions` auf das Ergebnis der Versuch, einen angegebenen Speicherbereich aufzulisten, die im Debugger zu melden.</span><span class="sxs-lookup"><span data-stu-id="1348c-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1348c-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1348c-109">Requirements</span></span>  
 <span data-ttu-id="1348c-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1348c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1348c-111">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="1348c-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="1348c-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1348c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1348c-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1348c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1348c-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1348c-114">See Also</span></span>  
 [<span data-ttu-id="1348c-115">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="1348c-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
