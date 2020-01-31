---
title: ICLRDataTarget::GetPointerSize-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetPointerSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetPointerSize
helpviewer_keywords:
- GetPointerSize method [.NET Framework debugging]
- ICLRDataTarget::GetPointerSize method [.NET Framework debugging]
ms.assetid: 51d9f4a4-81a7-4527-8537-5212bdb05c70
topic_type:
- apiref
ms.openlocfilehash: 7a274aaec4919b86f32f98e4d8278dc12748fb2b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785479"
---
# <a name="iclrdatatargetgetpointersize-method"></a><span data-ttu-id="d5c82-102">ICLRDataTarget::GetPointerSize-Methode</span><span class="sxs-lookup"><span data-stu-id="d5c82-102">ICLRDataTarget::GetPointerSize Method</span></span>
<span data-ttu-id="d5c82-103">Ruft die Größe (in Bytes) des Zeiger Typs ab, der vom Ziel Prozess verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d5c82-103">Gets the size, in bytes, of the pointer type that the target process uses.</span></span> <span data-ttu-id="d5c82-104">Diese Methode wird vom Common Language Runtime Data Access Services aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="d5c82-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5c82-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d5c82-105">Syntax</span></span>  
  
```cpp  
HRESULT GetPointerSize (  
    [out] ULONG32     *pointerSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5c82-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="d5c82-106">Parameters</span></span>  
 `pointerSize`  
 <span data-ttu-id="d5c82-107">vorgenommen Ein Zeiger auf einen ganzzahligen Wert, der die Größe eines Zeigers auf dem Ziel Prozess in Bytes angibt.</span><span class="sxs-lookup"><span data-stu-id="d5c82-107">[out] A pointer to an integer value that specifies the size, in bytes, of a pointer on the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5c82-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d5c82-108">Remarks</span></span>  
 <span data-ttu-id="d5c82-109">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="d5c82-109">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5c82-110">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d5c82-110">Requirements</span></span>  
 <span data-ttu-id="d5c82-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5c82-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5c82-112">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="d5c82-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="d5c82-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5c82-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5c82-114">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5c82-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5c82-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5c82-115">See also</span></span>

- [<span data-ttu-id="d5c82-116">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5c82-116">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
