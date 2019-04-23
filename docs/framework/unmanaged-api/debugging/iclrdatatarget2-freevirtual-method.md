---
title: ICLRDataTarget2::FreeVirtual-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b30bd3e97af8d222f629c5b4f9f318a9b6379e78
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59181401"
---
# <a name="iclrdatatarget2freevirtual-method"></a><span data-ttu-id="699b3-102">ICLRDataTarget2::FreeVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="699b3-102">ICLRDataTarget2::FreeVirtual Method</span></span>
<span data-ttu-id="699b3-103">Wird aufgerufen, durch die common Language Runtime (CLR) Datenzugriffsdiensten der um Arbeitsspeicher freizugeben, der zuvor im Adressbereich des Zielprozesses zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="699b3-103">Called by the common language runtime (CLR) data access services to free memory that was previously allocated in the address space of the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="699b3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="699b3-104">Syntax</span></span>  
  
```  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="699b3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="699b3-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="699b3-106">[in] Ein `CLRDATA_ADDRESS` Wert, der angibt, die Startadresse des Arbeitsspeichers freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="699b3-106">[in] A `CLRDATA_ADDRESS` value that specifies the starting address of the memory to be freed.</span></span>  
  
 `size`  
 <span data-ttu-id="699b3-107">[in] Die Größe in Bytes, des Arbeitsspeichers freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="699b3-107">[in] The size, in bytes, of the memory to be freed.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="699b3-108">[in] Flags, die das Freigeben von Arbeitsspeicher zu steuern.</span><span class="sxs-lookup"><span data-stu-id="699b3-108">[in] Flags that control the freeing of memory.</span></span> <span data-ttu-id="699b3-109">Finden Sie unter Win32 `VirtualFree` Funktion.</span><span class="sxs-lookup"><span data-stu-id="699b3-109">See the Win32 `VirtualFree` function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="699b3-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="699b3-110">Remarks</span></span>  
 <span data-ttu-id="699b3-111">Die `FreeVirtual` Methode dient als ein logischer Wrapper für die Win32- `VirtualFree` Funktion.</span><span class="sxs-lookup"><span data-stu-id="699b3-111">The `FreeVirtual` method serves as a logical wrapper for the Win32 `VirtualFree` function.</span></span>  
  
 <span data-ttu-id="699b3-112">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="699b3-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="699b3-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="699b3-113">Requirements</span></span>  
 <span data-ttu-id="699b3-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="699b3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="699b3-115">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="699b3-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="699b3-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="699b3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="699b3-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="699b3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="699b3-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="699b3-118">See also</span></span>

- [<span data-ttu-id="699b3-119">ICLRDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="699b3-119">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [<span data-ttu-id="699b3-120">AllocVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="699b3-120">AllocVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)
