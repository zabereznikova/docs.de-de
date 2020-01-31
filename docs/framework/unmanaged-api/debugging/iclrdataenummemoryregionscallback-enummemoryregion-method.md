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
ms.openlocfilehash: c8313b7c97eb5d94424259dc91459f62e13368fb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785596"
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a><span data-ttu-id="c0db9-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion-Methode</span><span class="sxs-lookup"><span data-stu-id="c0db9-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion Method</span></span>
<span data-ttu-id="c0db9-103">Wird von [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) aufgerufen, um dem Debugger das Ergebnis eines Versuchs, einen angegebenen Bereich des Speichers aufzulisten, zu melden.</span><span class="sxs-lookup"><span data-stu-id="c0db9-103">Called by [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0db9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c0db9-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0db9-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="c0db9-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="c0db9-106">in Die Startadresse des Speicherbereichs, der aufgelistet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c0db9-106">[in] The starting address of the memory region that was to be enumerated.</span></span>  
  
 `size`  
 <span data-ttu-id="c0db9-107">in Die Größe des Arbeitsspeicher Bereichs in Bytes.</span><span class="sxs-lookup"><span data-stu-id="c0db9-107">[in] The size, in bytes, of the memory region.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0db9-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c0db9-108">Remarks</span></span>  
 <span data-ttu-id="c0db9-109">Die `ICLRDataEnumMemoryRegions::EnumMemoryRegions`-Methode ruft diese Rückruf Methode nach jedem Versuch auf, einen Speicherbereich aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="c0db9-109">The `ICLRDataEnumMemoryRegions::EnumMemoryRegions` method will call this callback method after each attempt to enumerate a memory region.</span></span> <span data-ttu-id="c0db9-110">Die Enumeration wird auch dann fortgesetzt, wenn diese Methode ein HRESULT zurückgibt, das einen Fehler angibt.</span><span class="sxs-lookup"><span data-stu-id="c0db9-110">The enumeration will continue even if this method returns an HRESULT indicating failure.</span></span>  
  
 <span data-ttu-id="c0db9-111">Die von diesem Rückruf gemeldeten Regionen können Duplikate oder überlappende Bereiche sein.</span><span class="sxs-lookup"><span data-stu-id="c0db9-111">Regions reported by this callback may be duplicates or overlapping regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0db9-112">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c0db9-112">Requirements</span></span>  
 <span data-ttu-id="c0db9-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0db9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0db9-114">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="c0db9-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c0db9-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0db9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0db9-116">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0db9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0db9-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0db9-117">See also</span></span>

- [<span data-ttu-id="c0db9-118">ICLRDataEnumMemoryRegionsCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0db9-118">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](iclrdataenummemoryregionscallback-interface.md)
