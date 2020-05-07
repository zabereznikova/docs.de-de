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
ms.openlocfilehash: 0a36af5b411673081e74aa243ec8e0f8f876f238
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860476"
---
# <a name="iclrdatatarget2freevirtual-method"></a><span data-ttu-id="2fa13-102">ICLRDataTarget2::FreeVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="2fa13-102">ICLRDataTarget2::FreeVirtual Method</span></span>
<span data-ttu-id="2fa13-103">Wird von den Common Language Runtime (CLR)-Datenzugriffs Diensten aufgerufen, um Arbeitsspeicher freizugeben, der zuvor im Adressraum des Ziel Prozesses belegt wurde.</span><span class="sxs-lookup"><span data-stu-id="2fa13-103">Called by the common language runtime (CLR) data access services to free memory that was previously allocated in the address space of the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fa13-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2fa13-104">Syntax</span></span>  
  
```cpp  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fa13-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2fa13-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="2fa13-106">in Ein `CLRDATA_ADDRESS` -Wert, der die Startadresse des frei zufügenden Speichers angibt.</span><span class="sxs-lookup"><span data-stu-id="2fa13-106">[in] A `CLRDATA_ADDRESS` value that specifies the starting address of the memory to be freed.</span></span>  
  
 `size`  
 <span data-ttu-id="2fa13-107">in Die Größe des frei zufügenden Speichers in Byte.</span><span class="sxs-lookup"><span data-stu-id="2fa13-107">[in] The size, in bytes, of the memory to be freed.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="2fa13-108">in Flags, die die Freigabe von Arbeitsspeicher steuern.</span><span class="sxs-lookup"><span data-stu-id="2fa13-108">[in] Flags that control the freeing of memory.</span></span> <span data-ttu-id="2fa13-109">Siehe die Win32 `VirtualFree` -Funktion.</span><span class="sxs-lookup"><span data-stu-id="2fa13-109">See the Win32 `VirtualFree` function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2fa13-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2fa13-110">Remarks</span></span>  
 <span data-ttu-id="2fa13-111">Die `FreeVirtual` -Methode dient als logischer Wrapper für die Win32 `VirtualFree` -Funktion.</span><span class="sxs-lookup"><span data-stu-id="2fa13-111">The `FreeVirtual` method serves as a logical wrapper for the Win32 `VirtualFree` function.</span></span>  
  
 <span data-ttu-id="2fa13-112">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="2fa13-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fa13-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2fa13-113">Requirements</span></span>  
 <span data-ttu-id="2fa13-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fa13-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fa13-115">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="2fa13-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="2fa13-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2fa13-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2fa13-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fa13-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fa13-118">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="2fa13-118">See also</span></span>

- [<span data-ttu-id="2fa13-119">ICLRDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2fa13-119">ICLRDataTarget2 Interface</span></span>](iclrdatatarget2-interface.md)
- [<span data-ttu-id="2fa13-120">AllocVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="2fa13-120">AllocVirtual Method</span></span>](iclrdatatarget2-allocvirtual-method.md)
