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
ms.openlocfilehash: ddcb8064dfb9be30c66404a8762a9ca73cd6afe4
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860665"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="b77a0-102">ICLRDataEnumMemoryRegionsCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b77a0-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="b77a0-103">Stellt eine Rückruf Methode für [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) bereit, um dem Debugger das Ergebnis eines Versuchs zum Auflisten eines bestimmten Speicherbereichs zu melden.</span><span class="sxs-lookup"><span data-stu-id="b77a0-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b77a0-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="b77a0-104">Methods</span></span>  
  
|<span data-ttu-id="b77a0-105">Methode</span><span class="sxs-lookup"><span data-stu-id="b77a0-105">Method</span></span>|<span data-ttu-id="b77a0-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b77a0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b77a0-107">EnumMemoryRegion-Methode</span><span class="sxs-lookup"><span data-stu-id="b77a0-107">EnumMemoryRegion Method</span></span>](iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="b77a0-108">Wird von `ICLRDataEnumMemoryRegions::EnumMemoryRegions` aufgerufen, um dem Debugger das Ergebnis eines Versuchs, einen angegebenen Bereich des Speichers aufzulisten, zu melden.</span><span class="sxs-lookup"><span data-stu-id="b77a0-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b77a0-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b77a0-109">Requirements</span></span>  
 <span data-ttu-id="b77a0-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b77a0-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b77a0-111">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="b77a0-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="b77a0-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b77a0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b77a0-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b77a0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b77a0-114">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="b77a0-114">See also</span></span>

- [<span data-ttu-id="b77a0-115">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b77a0-115">Debugging Interfaces</span></span>](debugging-interfaces.md)
