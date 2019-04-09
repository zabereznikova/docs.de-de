---
title: ICLRDataEnumMemoryRegions::EnumMemoryRegions-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegions.EnumMemoryRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions
helpviewer_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions method [.NET Framework debugging]
- EnumMemoryRegions method [.NET Framework debugging]
ms.assetid: 22d2e339-f174-40b5-a478-0b744501566f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 886f78a0561ebbd5470b7932123f67975d650693
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197346"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a><span data-ttu-id="844cc-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions-Methode</span><span class="sxs-lookup"><span data-stu-id="844cc-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions Method</span></span>
<span data-ttu-id="844cc-103">Listet die angegebenen Bereiche des Arbeitsspeichers.</span><span class="sxs-lookup"><span data-stu-id="844cc-103">Enumerates specified areas of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="844cc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="844cc-104">Syntax</span></span>  
  
```  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="844cc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="844cc-105">Parameters</span></span>  
 `callback`  
 <span data-ttu-id="844cc-106">[in] Ein Zeiger auf ein [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) -Instanz, die von dieser Methode für jeden Speicherbereich aufgezählt werden, um den Debugger des Ergebnisses benachrichtigen aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="844cc-106">[in] A pointer to an [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance that is called by this method for each memory region being enumerated to notify the debugger of the result.</span></span>  
  
 <span data-ttu-id="844cc-107">Die Enumeration von Speicherbereiche wird fortgesetzt, selbst wenn der Rückruf ein Fehler weist darauf hin.</span><span class="sxs-lookup"><span data-stu-id="844cc-107">The enumeration of memory regions continues even if the callback indicates a failure.</span></span>  
  
 `miniDumpFlags`  
 <span data-ttu-id="844cc-108">[in] Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="844cc-108">[in] Not used.</span></span>  
  
 `clrFlags`  
 <span data-ttu-id="844cc-109">[in] Der Wert der [CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) Enumeration, der angibt, die Bereiche des Arbeitsspeichers aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="844cc-109">[in] A value of the [CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) enumeration that specifies the regions of memory to be enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="844cc-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="844cc-110">Remarks</span></span>  
 <span data-ttu-id="844cc-111">Diese Methode verwendet die angegebene [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) Instanz an den Aufrufer der Ergebnisse zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="844cc-111">This method uses the specified [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance to notify the caller of results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="844cc-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="844cc-112">Requirements</span></span>  
 <span data-ttu-id="844cc-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="844cc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="844cc-114">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="844cc-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="844cc-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="844cc-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="844cc-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="844cc-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="844cc-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="844cc-117">See also</span></span>

- [<span data-ttu-id="844cc-118">ICLRDataEnumMemoryRegions-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="844cc-118">ICLRDataEnumMemoryRegions Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)
