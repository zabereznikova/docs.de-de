---
title: ICLRDataTarget2::AllocVirtual-Methode
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6d869b350217903dda209699f94897b70bc57132
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatarget2allocvirtual-method"></a><span data-ttu-id="bed7e-102">ICLRDataTarget2::AllocVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="bed7e-102">ICLRDataTarget2::AllocVirtual Method</span></span>
<span data-ttu-id="bed7e-103">Wird von der common Language Runtime (CLR) Datenzugriffsdiensten der belegen von Speicher im Adressraum dieses Zielprozesses aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="bed7e-103">Called by the common language runtime (CLR) data access services to allocate memory in the address space of this target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bed7e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bed7e-104">Syntax</span></span>  
  
```  
HRESULT AllocVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags,  
    [in] ULONG32 protectFlags,  
    [out] CLRDATA_ADDRESS* virt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bed7e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bed7e-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="bed7e-106">[in] Ein `CLRDATA_ADDRESS` Wert, der angibt, die angeforderte Startadresse des Arbeitsspeichers zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="bed7e-106">[in] A `CLRDATA_ADDRESS` value that specifies the requested starting address of the memory to be allocated.</span></span>  
  
 `size`  
 <span data-ttu-id="bed7e-107">[in] Die Größe in Bytes, des Arbeitsspeichers zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="bed7e-107">[in] The size, in bytes, of the memory to be allocated.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="bed7e-108">[in] Flags, die die Belegung von Speicher zu steuern.</span><span class="sxs-lookup"><span data-stu-id="bed7e-108">[in] Flags that control the allocation of memory.</span></span> <span data-ttu-id="bed7e-109">Finden Sie unter Win32 `VirtualAlloc` Funktion.</span><span class="sxs-lookup"><span data-stu-id="bed7e-109">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `protectFlags`  
 <span data-ttu-id="bed7e-110">[in] Die Schutzattribute für den reservierten Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="bed7e-110">[in] The protection attributes for the allocated memory.</span></span> <span data-ttu-id="bed7e-111">Finden Sie unter Win32 `VirtualAlloc` Funktion.</span><span class="sxs-lookup"><span data-stu-id="bed7e-111">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `virt`  
 <span data-ttu-id="bed7e-112">[out] Ein Zeiger auf eine `CLRDATA_ADDRESS` -Wert, der die eigentliche Startadresse des belegten angibt.</span><span class="sxs-lookup"><span data-stu-id="bed7e-112">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the actual starting address of the allocated memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bed7e-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bed7e-113">Remarks</span></span>  
 <span data-ttu-id="bed7e-114">Die `AllocVirtual` Methode dient als logischer Wrapper für die Win32- `VirtualAlloc` Funktion.</span><span class="sxs-lookup"><span data-stu-id="bed7e-114">The `AllocVirtual` method serves as a logical wrapper for the Win32 `VirtualAlloc` function.</span></span>  
  
 <span data-ttu-id="bed7e-115">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="bed7e-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bed7e-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bed7e-116">Requirements</span></span>  
 <span data-ttu-id="bed7e-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bed7e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bed7e-118">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="bed7e-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="bed7e-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bed7e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bed7e-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bed7e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bed7e-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bed7e-121">See Also</span></span>  
 [<span data-ttu-id="bed7e-122">ICLRDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bed7e-122">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [<span data-ttu-id="bed7e-123">FreeVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="bed7e-123">FreeVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)
