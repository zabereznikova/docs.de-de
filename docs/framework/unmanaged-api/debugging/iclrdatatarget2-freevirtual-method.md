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
ms.openlocfilehash: 1fb701a40abe2dc6e51443837c07ee5ba05ddfbe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723648"
---
# <a name="iclrdatatarget2freevirtual-method"></a><span data-ttu-id="70bef-102">ICLRDataTarget2::FreeVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="70bef-102">ICLRDataTarget2::FreeVirtual Method</span></span>

<span data-ttu-id="70bef-103">Wird von den Common Language Runtime (CLR)-Datenzugriffs Diensten aufgerufen, um Arbeitsspeicher freizugeben, der zuvor im Adressraum des Ziel Prozesses belegt wurde.</span><span class="sxs-lookup"><span data-stu-id="70bef-103">Called by the common language runtime (CLR) data access services to free memory that was previously allocated in the address space of the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70bef-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="70bef-104">Syntax</span></span>  
  
```cpp  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70bef-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="70bef-105">Parameters</span></span>  

 `addr`  
 <span data-ttu-id="70bef-106">in Ein- `CLRDATA_ADDRESS` Wert, der die Startadresse des frei zufügenden Speichers angibt.</span><span class="sxs-lookup"><span data-stu-id="70bef-106">[in] A `CLRDATA_ADDRESS` value that specifies the starting address of the memory to be freed.</span></span>  
  
 `size`  
 <span data-ttu-id="70bef-107">in Die Größe des frei zufügenden Speichers in Byte.</span><span class="sxs-lookup"><span data-stu-id="70bef-107">[in] The size, in bytes, of the memory to be freed.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="70bef-108">in Flags, die die Freigabe von Arbeitsspeicher steuern.</span><span class="sxs-lookup"><span data-stu-id="70bef-108">[in] Flags that control the freeing of memory.</span></span> <span data-ttu-id="70bef-109">Siehe die Win32- `VirtualFree` Funktion.</span><span class="sxs-lookup"><span data-stu-id="70bef-109">See the Win32 `VirtualFree` function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70bef-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="70bef-110">Remarks</span></span>  

 <span data-ttu-id="70bef-111">Die- `FreeVirtual` Methode dient als logischer Wrapper für die Win32- `VirtualFree` Funktion.</span><span class="sxs-lookup"><span data-stu-id="70bef-111">The `FreeVirtual` method serves as a logical wrapper for the Win32 `VirtualFree` function.</span></span>  
  
 <span data-ttu-id="70bef-112">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="70bef-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70bef-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="70bef-113">Requirements</span></span>  

 <span data-ttu-id="70bef-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70bef-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70bef-115">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="70bef-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="70bef-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70bef-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70bef-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70bef-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70bef-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="70bef-118">See also</span></span>

- [<span data-ttu-id="70bef-119">ICLRDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="70bef-119">ICLRDataTarget2 Interface</span></span>](iclrdatatarget2-interface.md)
- [<span data-ttu-id="70bef-120">AllocVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="70bef-120">AllocVirtual Method</span></span>](iclrdatatarget2-allocvirtual-method.md)
