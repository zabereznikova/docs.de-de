---
title: ICLRDataTarget::ReadVirtual-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.ReadVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::ReadVirtual
helpviewer_keywords:
- ReadVirtual method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::ReadVirtual method [.NET Framework debugging]
ms.assetid: da3769eb-1828-4aa1-b9ed-db4842136a43
topic_type:
- apiref
ms.openlocfilehash: 0332fae46d6a65cfb7cc0b929cc2fd0d97e1790e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179148"
---
# <a name="iclrdatatargetreadvirtual-method"></a><span data-ttu-id="77813-102">ICLRDataTarget::ReadVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="77813-102">ICLRDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="77813-103">Liest Daten aus der angegebenen virtuellen Speicheradresse in den angegebenen Puffer.</span><span class="sxs-lookup"><span data-stu-id="77813-103">Reads data from the specified virtual memory address into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77813-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="77813-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [out, size_is(bytesRequested), length_is(*bytesRead)]
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77813-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="77813-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="77813-106">[in] Ein CLRDATA_ADDRESS, in dem die Adresse des virtuellen Speichers gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="77813-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="77813-107">[out] Ein Zeiger auf einen Puffer, der die Daten empfängt.</span><span class="sxs-lookup"><span data-stu-id="77813-107">[out] A pointer to a buffer that receives the data.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="77813-108">[in] Die Länge des Puffers.</span><span class="sxs-lookup"><span data-stu-id="77813-108">[in] The length of the buffer.</span></span>  
  
 `bytesRead`  
 <span data-ttu-id="77813-109">[out] Ein Zeiger auf die Anzahl der zurückgegebenen Bytes.</span><span class="sxs-lookup"><span data-stu-id="77813-109">[out] A pointer to the number of bytes returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77813-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="77813-110">Requirements</span></span>  
 <span data-ttu-id="77813-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77813-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77813-112">**Kopfzeile:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="77813-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="77813-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77813-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77813-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77813-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77813-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="77813-115">See also</span></span>

- [<span data-ttu-id="77813-116">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="77813-116">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
