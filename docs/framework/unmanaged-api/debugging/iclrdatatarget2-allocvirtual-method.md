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
ms.openlocfilehash: 7ba9200419d6b6fef467ae02bd74101414e125da
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091719"
---
# <a name="iclrdatatarget2allocvirtual-method"></a><span data-ttu-id="1e211-102">ICLRDataTarget2::AllocVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="1e211-102">ICLRDataTarget2::AllocVirtual Method</span></span>
<span data-ttu-id="1e211-103">Wird aufgerufen, durch die common Language Runtime (CLR) Datenzugriffsdiensten der Speicher im Adressraum dieses Prozesses Ziel reserviert werden.</span><span class="sxs-lookup"><span data-stu-id="1e211-103">Called by the common language runtime (CLR) data access services to allocate memory in the address space of this target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e211-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1e211-104">Syntax</span></span>  
  
```  
HRESULT AllocVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags,  
    [in] ULONG32 protectFlags,  
    [out] CLRDATA_ADDRESS* virt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e211-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1e211-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="1e211-106">[in] Ein `CLRDATA_ADDRESS` Wert, der angibt, der die angeforderte Startadresse des Arbeitsspeichers, die zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="1e211-106">[in] A `CLRDATA_ADDRESS` value that specifies the requested starting address of the memory to be allocated.</span></span>  
  
 `size`  
 <span data-ttu-id="1e211-107">[in] Die Größe in Bytes, des Arbeitsspeichers, die zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="1e211-107">[in] The size, in bytes, of the memory to be allocated.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="1e211-108">[in] Flags, die die Zuordnung von Arbeitsspeicher zu steuern.</span><span class="sxs-lookup"><span data-stu-id="1e211-108">[in] Flags that control the allocation of memory.</span></span> <span data-ttu-id="1e211-109">Finden Sie unter Win32 `VirtualAlloc` Funktion.</span><span class="sxs-lookup"><span data-stu-id="1e211-109">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `protectFlags`  
 <span data-ttu-id="1e211-110">[in] Die Schutzattribute für den zugeordneten Speicher.</span><span class="sxs-lookup"><span data-stu-id="1e211-110">[in] The protection attributes for the allocated memory.</span></span> <span data-ttu-id="1e211-111">Finden Sie unter Win32 `VirtualAlloc` Funktion.</span><span class="sxs-lookup"><span data-stu-id="1e211-111">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `virt`  
 <span data-ttu-id="1e211-112">[out] Ein Zeiger auf eine `CLRDATA_ADDRESS` -Wert, der die eigentliche Startadresse des zugeordneten Speichers angibt.</span><span class="sxs-lookup"><span data-stu-id="1e211-112">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the actual starting address of the allocated memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e211-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1e211-113">Remarks</span></span>  
 <span data-ttu-id="1e211-114">Die `AllocVirtual` Methode dient als ein logischer Wrapper für die Win32- `VirtualAlloc` Funktion.</span><span class="sxs-lookup"><span data-stu-id="1e211-114">The `AllocVirtual` method serves as a logical wrapper for the Win32 `VirtualAlloc` function.</span></span>  
  
 <span data-ttu-id="1e211-115">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="1e211-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e211-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1e211-116">Requirements</span></span>  
 <span data-ttu-id="1e211-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e211-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e211-118">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="1e211-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="1e211-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e211-119">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="1e211-120">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="1e211-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1e211-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e211-121">See also</span></span>

- [<span data-ttu-id="1e211-122">ICLRDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1e211-122">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [<span data-ttu-id="1e211-123">FreeVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="1e211-123">FreeVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)
