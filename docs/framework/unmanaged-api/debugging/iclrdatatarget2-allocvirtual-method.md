---
title: ICLRDataTarget2::AllocVirtual-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.AllocVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::AllocVirtual
helpviewer_keywords:
- ICLRDataTarget2::AllocVirtual method [.NET Framework debugging]
- AllocVirtual method [.NET Framework debugging]
ms.assetid: e3226230-964b-47fb-9f53-d6fdbeda1e9e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 92eff65078f05557f542c64c1be7d4f6eca43eb5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738468"
---
# <a name="iclrdatatarget2allocvirtual-method"></a><span data-ttu-id="e90bb-102">ICLRDataTarget2::AllocVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="e90bb-102">ICLRDataTarget2::AllocVirtual Method</span></span>
<span data-ttu-id="e90bb-103">Wird aufgerufen, durch die common Language Runtime (CLR) Datenzugriffsdiensten der Speicher im Adressraum dieses Prozesses Ziel reserviert werden.</span><span class="sxs-lookup"><span data-stu-id="e90bb-103">Called by the common language runtime (CLR) data access services to allocate memory in the address space of this target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e90bb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e90bb-104">Syntax</span></span>  
  
```cpp  
HRESULT AllocVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags,  
    [in] ULONG32 protectFlags,  
    [out] CLRDATA_ADDRESS* virt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e90bb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e90bb-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="e90bb-106">[in] Ein `CLRDATA_ADDRESS` Wert, der angibt, der die angeforderte Startadresse des Arbeitsspeichers, die zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="e90bb-106">[in] A `CLRDATA_ADDRESS` value that specifies the requested starting address of the memory to be allocated.</span></span>  
  
 `size`  
 <span data-ttu-id="e90bb-107">[in] Die Größe in Bytes, des Arbeitsspeichers, die zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="e90bb-107">[in] The size, in bytes, of the memory to be allocated.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="e90bb-108">[in] Flags, die die Zuordnung von Arbeitsspeicher zu steuern.</span><span class="sxs-lookup"><span data-stu-id="e90bb-108">[in] Flags that control the allocation of memory.</span></span> <span data-ttu-id="e90bb-109">Finden Sie unter Win32 `VirtualAlloc` Funktion.</span><span class="sxs-lookup"><span data-stu-id="e90bb-109">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `protectFlags`  
 <span data-ttu-id="e90bb-110">[in] Die Schutzattribute für den zugeordneten Speicher.</span><span class="sxs-lookup"><span data-stu-id="e90bb-110">[in] The protection attributes for the allocated memory.</span></span> <span data-ttu-id="e90bb-111">Finden Sie unter Win32 `VirtualAlloc` Funktion.</span><span class="sxs-lookup"><span data-stu-id="e90bb-111">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `virt`  
 <span data-ttu-id="e90bb-112">[out] Ein Zeiger auf eine `CLRDATA_ADDRESS` -Wert, der die eigentliche Startadresse des zugeordneten Speichers angibt.</span><span class="sxs-lookup"><span data-stu-id="e90bb-112">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the actual starting address of the allocated memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e90bb-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e90bb-113">Remarks</span></span>  
 <span data-ttu-id="e90bb-114">Die `AllocVirtual` Methode dient als ein logischer Wrapper für die Win32- `VirtualAlloc` Funktion.</span><span class="sxs-lookup"><span data-stu-id="e90bb-114">The `AllocVirtual` method serves as a logical wrapper for the Win32 `VirtualAlloc` function.</span></span>  
  
 <span data-ttu-id="e90bb-115">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="e90bb-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e90bb-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e90bb-116">Requirements</span></span>  
 <span data-ttu-id="e90bb-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e90bb-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e90bb-118">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="e90bb-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="e90bb-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e90bb-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e90bb-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e90bb-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e90bb-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e90bb-121">See also</span></span>

- [<span data-ttu-id="e90bb-122">ICLRDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e90bb-122">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [<span data-ttu-id="e90bb-123">FreeVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="e90bb-123">FreeVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)
