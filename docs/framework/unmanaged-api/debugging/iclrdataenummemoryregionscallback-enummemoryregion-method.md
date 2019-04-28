---
title: ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback.EnumMemoryRegion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
helpviewer_keywords:
- EnumMemoryRegion method [.NET Framework debugging]
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion method [.NET Framework debugging]
ms.assetid: 9bb93fab-57e8-4f9a-9ef3-1794504fa896
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85b1c5455cb2008a352461d6b506e43fcef48d17
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698238"
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a><span data-ttu-id="97068-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion-Methode</span><span class="sxs-lookup"><span data-stu-id="97068-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion Method</span></span>
<span data-ttu-id="97068-103">Wird aufgerufen, indem [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) zum Berichten an den Debugger des Ergebnis der Versuch, einen angegebenen Speicherbereich aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="97068-103">Called by [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97068-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="97068-104">Syntax</span></span>  
  
```  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97068-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="97068-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="97068-106">[in] Die Startadresse des Arbeitsspeicherbereichs, die aufgelistet werden soll.</span><span class="sxs-lookup"><span data-stu-id="97068-106">[in] The starting address of the memory region that was to be enumerated.</span></span>  
  
 `size`  
 <span data-ttu-id="97068-107">[in] Die Größe des Arbeitsspeicherbereichs in Bytes.</span><span class="sxs-lookup"><span data-stu-id="97068-107">[in] The size, in bytes, of the memory region.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97068-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="97068-108">Remarks</span></span>  
 <span data-ttu-id="97068-109">Die `ICLRDataEnumMemoryRegions::EnumMemoryRegions` Methode wird diese Callback-Methode aufrufen, nach jedem Versuch, einen Speicher aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="97068-109">The `ICLRDataEnumMemoryRegions::EnumMemoryRegions` method will call this callback method after each attempt to enumerate a memory region.</span></span> <span data-ttu-id="97068-110">Die Enumeration wird fortgesetzt, selbst wenn diese Methode einen HRESULT-Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="97068-110">The enumeration will continue even if this method returns an HRESULT indicating failure.</span></span>  
  
 <span data-ttu-id="97068-111">Regionen, die von diesem Rückruf gemeldeten können es sich um Duplikate oder überlappende Bereiche sein.</span><span class="sxs-lookup"><span data-stu-id="97068-111">Regions reported by this callback may be duplicates or overlapping regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97068-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="97068-112">Requirements</span></span>  
 <span data-ttu-id="97068-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97068-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97068-114">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="97068-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="97068-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97068-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97068-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97068-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97068-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97068-117">See also</span></span>

- [<span data-ttu-id="97068-118">ICLRDataEnumMemoryRegionsCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="97068-118">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)
