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
ms.openlocfilehash: f080d852b190346740a3629f3b5d46a9f3808293
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703628"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="7ae68-102">ICLRDataEnumMemoryRegionsCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ae68-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>

<span data-ttu-id="7ae68-103">Stellt eine Rückruf Methode für [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) bereit, um dem Debugger das Ergebnis eines Versuchs zum Auflisten eines bestimmten Speicherbereichs zu melden.</span><span class="sxs-lookup"><span data-stu-id="7ae68-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7ae68-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="7ae68-104">Methods</span></span>  
  
|<span data-ttu-id="7ae68-105">Methode</span><span class="sxs-lookup"><span data-stu-id="7ae68-105">Method</span></span>|<span data-ttu-id="7ae68-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7ae68-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7ae68-107">EnumMemoryRegion-Methode</span><span class="sxs-lookup"><span data-stu-id="7ae68-107">EnumMemoryRegion Method</span></span>](iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="7ae68-108">Wird von aufgerufen, um dem `ICLRDataEnumMemoryRegions::EnumMemoryRegions` Debugger das Ergebnis eines Versuchs, einen angegebenen Bereich des Speichers aufzulisten, zu melden.</span><span class="sxs-lookup"><span data-stu-id="7ae68-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7ae68-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7ae68-109">Requirements</span></span>  

 <span data-ttu-id="7ae68-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ae68-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ae68-111">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="7ae68-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="7ae68-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ae68-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ae68-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ae68-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ae68-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7ae68-114">See also</span></span>

- [<span data-ttu-id="7ae68-115">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="7ae68-115">Debugging Interfaces</span></span>](debugging-interfaces.md)
