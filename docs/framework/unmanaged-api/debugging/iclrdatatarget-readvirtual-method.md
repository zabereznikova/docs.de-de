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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c9080a588b96c5b89c280a0fb407952bd580f26
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404222"
---
# <a name="iclrdatatargetreadvirtual-method"></a><span data-ttu-id="bb8d5-102">ICLRDataTarget::ReadVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="bb8d5-102">ICLRDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="bb8d5-103">Liest Daten aus der angegebenen virtuellen Speicheradresse in den angegebenen Puffer.</span><span class="sxs-lookup"><span data-stu-id="bb8d5-103">Reads data from the specified virtual memory address into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb8d5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb8d5-104">Syntax</span></span>  
  
```  
HRESULT ReadVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [out, size_is(bytesRequested), length_is(*bytesRead)]   
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesRead  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bb8d5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bb8d5-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="bb8d5-106">[in] Eine CLRDATA_ADDRESS, die Adresse des virtuellen Arbeitsspeichers speichert.</span><span class="sxs-lookup"><span data-stu-id="bb8d5-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="bb8d5-107">[out] Ein Zeiger auf einen Puffer, der die Daten empfängt.</span><span class="sxs-lookup"><span data-stu-id="bb8d5-107">[out] A pointer to a buffer that receives the data.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="bb8d5-108">[in] Die Länge des Puffers.</span><span class="sxs-lookup"><span data-stu-id="bb8d5-108">[in] The length of the buffer.</span></span>  
  
 `bytesRead`  
 <span data-ttu-id="bb8d5-109">[out] Ein Zeiger auf die Anzahl der Bytes, die zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="bb8d5-109">[out] A pointer to the number of bytes returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb8d5-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bb8d5-110">Requirements</span></span>  
 <span data-ttu-id="bb8d5-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb8d5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb8d5-112">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="bb8d5-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="bb8d5-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb8d5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb8d5-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb8d5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb8d5-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb8d5-115">See Also</span></span>  
 [<span data-ttu-id="bb8d5-116">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bb8d5-116">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
