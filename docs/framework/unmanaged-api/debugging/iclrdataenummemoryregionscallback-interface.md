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
ms.openlocfilehash: 4e3891996af5945ed95c8c37dddfee5c446db248
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789111"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="f3f0b-102">ICLRDataEnumMemoryRegionsCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f3f0b-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="f3f0b-103">Stellt eine Rückruf Methode für [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) bereit, um dem Debugger das Ergebnis eines Versuchs zum Auflisten eines bestimmten Speicherbereichs zu melden.</span><span class="sxs-lookup"><span data-stu-id="f3f0b-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f3f0b-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f3f0b-104">Methods</span></span>  
  
|<span data-ttu-id="f3f0b-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="f3f0b-105">Method</span></span>|<span data-ttu-id="f3f0b-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f3f0b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f3f0b-107">EnumMemoryRegion-Methode</span><span class="sxs-lookup"><span data-stu-id="f3f0b-107">EnumMemoryRegion Method</span></span>](iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="f3f0b-108">Wird von `ICLRDataEnumMemoryRegions::EnumMemoryRegions` aufgerufen, um dem Debugger zu melden, das Ergebnis eines Versuchs, einen angegebenen Bereich des Speichers aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="f3f0b-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f3f0b-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f3f0b-109">Requirements</span></span>  
 <span data-ttu-id="f3f0b-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3f0b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3f0b-111">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="f3f0b-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="f3f0b-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3f0b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3f0b-113">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3f0b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3f0b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3f0b-114">See also</span></span>

- [<span data-ttu-id="f3f0b-115">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f3f0b-115">Debugging Interfaces</span></span>](debugging-interfaces.md)
