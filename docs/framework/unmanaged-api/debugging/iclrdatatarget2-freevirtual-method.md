---
title: ICLRDataTarget2::FreeVirtual-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRDataTarget2.FreeVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::FreeVirtual
helpviewer_keywords:
- ICLRDataTarget::FreeVirtual method [.NET Framework debugging]
- FreeVirtual method [.NET Framework debugging]
ms.assetid: 26fb69f8-1467-4711-bd24-cb117c63938f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c6c52291d08af4c9537de6ca17d80f28870a6bc8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatarget2freevirtual-method"></a><span data-ttu-id="67078-102">ICLRDataTarget2::FreeVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="67078-102">ICLRDataTarget2::FreeVirtual Method</span></span>
<span data-ttu-id="67078-103">Wird aufgerufen, von der common Language Runtime (CLR) Daten Access Services um Arbeitsspeicher freizugeben, der zuvor im Adressbereich des Zielprozesses belegt wurde.</span><span class="sxs-lookup"><span data-stu-id="67078-103">Called by the common language runtime (CLR) data access services to free memory that was previously allocated in the address space of the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67078-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="67078-104">Syntax</span></span>  
  
```  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="67078-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="67078-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="67078-106">[in] Ein `CLRDATA_ADDRESS` Wert, der die Startadresse des freizugebenden Speichers angibt.</span><span class="sxs-lookup"><span data-stu-id="67078-106">[in] A `CLRDATA_ADDRESS` value that specifies the starting address of the memory to be freed.</span></span>  
  
 `size`  
 <span data-ttu-id="67078-107">[in] Die Größe in Bytes, des Arbeitsspeichers, der freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="67078-107">[in] The size, in bytes, of the memory to be freed.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="67078-108">[in] Flags, die das Freigeben von Arbeitsspeicher zu steuern.</span><span class="sxs-lookup"><span data-stu-id="67078-108">[in] Flags that control the freeing of memory.</span></span> <span data-ttu-id="67078-109">Finden Sie unter Win32 `VirtualFree` Funktion.</span><span class="sxs-lookup"><span data-stu-id="67078-109">See the Win32 `VirtualFree` function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67078-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="67078-110">Remarks</span></span>  
 <span data-ttu-id="67078-111">Die `FreeVirtual` Methode dient als logischer Wrapper für die Win32- `VirtualFree` Funktion.</span><span class="sxs-lookup"><span data-stu-id="67078-111">The `FreeVirtual` method serves as a logical wrapper for the Win32 `VirtualFree` function.</span></span>  
  
 <span data-ttu-id="67078-112">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="67078-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67078-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="67078-113">Requirements</span></span>  
 <span data-ttu-id="67078-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67078-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67078-115">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="67078-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="67078-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67078-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67078-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67078-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67078-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67078-118">See Also</span></span>  
 [<span data-ttu-id="67078-119">ICLRDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="67078-119">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [<span data-ttu-id="67078-120">AllocVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="67078-120">AllocVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)
