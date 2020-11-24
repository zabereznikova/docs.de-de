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
ms.openlocfilehash: 386f975ab0bbbe804fda2bd7567acf24f69e77fb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676074"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a><span data-ttu-id="a6ee2-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions-Methode</span><span class="sxs-lookup"><span data-stu-id="a6ee2-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions Method</span></span>

<span data-ttu-id="a6ee2-103">Listet angegebene Speicherbereiche auf.</span><span class="sxs-lookup"><span data-stu-id="a6ee2-103">Enumerates specified areas of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6ee2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a6ee2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6ee2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a6ee2-105">Parameters</span></span>  

 `callback`  
 <span data-ttu-id="a6ee2-106">in Ein Zeiger auf eine [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) -Instanz, die von dieser Methode für jeden aufgezählten Speicherbereich aufgerufen wird, um den Debugger über das Ergebnis zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="a6ee2-106">[in] A pointer to an [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) instance that is called by this method for each memory region being enumerated to notify the debugger of the result.</span></span>  
  
 <span data-ttu-id="a6ee2-107">Die Enumeration der Speicherbereiche wird auch dann fortgesetzt, wenn der Rückruf auf einen Fehler hinweist.</span><span class="sxs-lookup"><span data-stu-id="a6ee2-107">The enumeration of memory regions continues even if the callback indicates a failure.</span></span>  
  
 `miniDumpFlags`  
 <span data-ttu-id="a6ee2-108">[in] Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="a6ee2-108">[in] Not used.</span></span>  
  
 `clrFlags`  
 <span data-ttu-id="a6ee2-109">in Ein Wert der [CLRDataEnumMemoryFlags](clrdataenummemoryflags-enumeration.md) -Enumeration, der die aufzuzählenden Speicherbereiche angibt.</span><span class="sxs-lookup"><span data-stu-id="a6ee2-109">[in] A value of the [CLRDataEnumMemoryFlags](clrdataenummemoryflags-enumeration.md) enumeration that specifies the regions of memory to be enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6ee2-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a6ee2-110">Remarks</span></span>  

 <span data-ttu-id="a6ee2-111">Diese Methode verwendet die angegebene [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) -Instanz, um den Aufrufer über Ergebnisse zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="a6ee2-111">This method uses the specified [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) instance to notify the caller of results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6ee2-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a6ee2-112">Requirements</span></span>  

 <span data-ttu-id="a6ee2-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6ee2-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6ee2-114">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="a6ee2-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="a6ee2-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6ee2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6ee2-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6ee2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6ee2-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a6ee2-117">See also</span></span>

- [<span data-ttu-id="a6ee2-118">ICLRDataEnumMemoryRegions-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a6ee2-118">ICLRDataEnumMemoryRegions Interface</span></span>](iclrdataenummemoryregions-interface.md)
