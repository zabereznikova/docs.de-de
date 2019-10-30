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
ms.openlocfilehash: 7640f7fafd0bf52a302ac0da1e5df39b5da22d68
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73091145"
---
# <a name="iclrdatatarget2allocvirtual-method"></a><span data-ttu-id="e2d9c-102">ICLRDataTarget2::AllocVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="e2d9c-102">ICLRDataTarget2::AllocVirtual Method</span></span>
<span data-ttu-id="e2d9c-103">Wird von den Common Language Runtime (CLR)-Datenzugriffs Diensten aufgerufen, um Speicher im Adressraum dieses Ziel Prozesses zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="e2d9c-103">Called by the common language runtime (CLR) data access services to allocate memory in the address space of this target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2d9c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2d9c-104">Syntax</span></span>  
  
```cpp  
HRESULT AllocVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags,  
    [in] ULONG32 protectFlags,  
    [out] CLRDATA_ADDRESS* virt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2d9c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e2d9c-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="e2d9c-106">in Ein `CLRDATA_ADDRESS` Wert, der die angeforderte Startadresse des zugeordneten Speichers angibt.</span><span class="sxs-lookup"><span data-stu-id="e2d9c-106">[in] A `CLRDATA_ADDRESS` value that specifies the requested starting address of the memory to be allocated.</span></span>  
  
 `size`  
 <span data-ttu-id="e2d9c-107">in Die Größe des zugeordneten Speichers in Byte.</span><span class="sxs-lookup"><span data-stu-id="e2d9c-107">[in] The size, in bytes, of the memory to be allocated.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="e2d9c-108">in Flags, die die Speicher Belegung steuern.</span><span class="sxs-lookup"><span data-stu-id="e2d9c-108">[in] Flags that control the allocation of memory.</span></span> <span data-ttu-id="e2d9c-109">Weitere Informationen finden Sie unter Win32-`VirtualAlloc` Funktion.</span><span class="sxs-lookup"><span data-stu-id="e2d9c-109">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `protectFlags`  
 <span data-ttu-id="e2d9c-110">in Die Schutz Attribute für den zugewiesenen Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="e2d9c-110">[in] The protection attributes for the allocated memory.</span></span> <span data-ttu-id="e2d9c-111">Weitere Informationen finden Sie unter Win32-`VirtualAlloc` Funktion.</span><span class="sxs-lookup"><span data-stu-id="e2d9c-111">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `virt`  
 <span data-ttu-id="e2d9c-112">vorgenommen Ein Zeiger auf einen `CLRDATA_ADDRESS` Wert, der die tatsächliche Startadresse des zugeordneten Speichers angibt.</span><span class="sxs-lookup"><span data-stu-id="e2d9c-112">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the actual starting address of the allocated memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2d9c-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e2d9c-113">Remarks</span></span>  
 <span data-ttu-id="e2d9c-114">Die `AllocVirtual`-Methode dient als logischer Wrapper für die Win32-`VirtualAlloc`-Funktion.</span><span class="sxs-lookup"><span data-stu-id="e2d9c-114">The `AllocVirtual` method serves as a logical wrapper for the Win32 `VirtualAlloc` function.</span></span>  
  
 <span data-ttu-id="e2d9c-115">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="e2d9c-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2d9c-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e2d9c-116">Requirements</span></span>  
 <span data-ttu-id="e2d9c-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2d9c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2d9c-118">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="e2d9c-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="e2d9c-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2d9c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2d9c-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2d9c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2d9c-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2d9c-121">See also</span></span>

- [<span data-ttu-id="e2d9c-122">ICLRDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e2d9c-122">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [<span data-ttu-id="e2d9c-123">FreeVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="e2d9c-123">FreeVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)
