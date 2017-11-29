---
title: ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataEnumMemoryRegionsCallback.EnumMemoryRegion
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
helpviewer_keywords:
- EnumMemoryRegion method [.NET Framework debugging]
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion method [.NET Framework debugging]
ms.assetid: 9bb93fab-57e8-4f9a-9ef3-1794504fa896
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1b1897b18a8dcbb261a5041ca8b530b7877b910
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a><span data-ttu-id="8fe3a-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion-Methode</span><span class="sxs-lookup"><span data-stu-id="8fe3a-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion Method</span></span>
<span data-ttu-id="8fe3a-103">Wird aufgerufen, indem [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) auf das Ergebnis der Versuch, einen angegebenen Speicherbereich aufzulisten, die im Debugger zu melden.</span><span class="sxs-lookup"><span data-stu-id="8fe3a-103">Called by [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fe3a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8fe3a-104">Syntax</span></span>  
  
```  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8fe3a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8fe3a-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="8fe3a-106">[in] Die Startadresse des Arbeitsspeicherbereichs, der aufgelistet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8fe3a-106">[in] The starting address of the memory region that was to be enumerated.</span></span>  
  
 `size`  
 <span data-ttu-id="8fe3a-107">[in] Die Größe des Arbeitsspeicherbereichs in Bytes.</span><span class="sxs-lookup"><span data-stu-id="8fe3a-107">[in] The size, in bytes, of the memory region.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8fe3a-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8fe3a-108">Remarks</span></span>  
 <span data-ttu-id="8fe3a-109">Die `ICLRDataEnumMemoryRegions::EnumMemoryRegions` Methode ruft diese Rückrufmethode nach jedem Versuch, einen Arbeitsspeicherbereich aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="8fe3a-109">The `ICLRDataEnumMemoryRegions::EnumMemoryRegions` method will call this callback method after each attempt to enumerate a memory region.</span></span> <span data-ttu-id="8fe3a-110">Die Enumeration wird fortgesetzt, auch wenn diese Methode gibt einen HRESULT-Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="8fe3a-110">The enumeration will continue even if this method returns an HRESULT indicating failure.</span></span>  
  
 <span data-ttu-id="8fe3a-111">Bereiche, die von diesem Rückruf gemeldeten möglicherweise Duplikate oder überlappende Bereiche.</span><span class="sxs-lookup"><span data-stu-id="8fe3a-111">Regions reported by this callback may be duplicates or overlapping regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fe3a-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8fe3a-112">Requirements</span></span>  
 <span data-ttu-id="8fe3a-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fe3a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fe3a-114">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="8fe3a-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="8fe3a-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8fe3a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8fe3a-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fe3a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fe3a-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8fe3a-117">See Also</span></span>  
 <span data-ttu-id="8fe3a-118">[[ICLRDataEnumMemoryRegionsCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="8fe3a-118">[ICLRDataEnumMemoryRegionsCallback Interface](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)</span></span>
