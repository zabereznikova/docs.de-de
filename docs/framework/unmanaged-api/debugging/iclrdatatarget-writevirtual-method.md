---
title: ICLRDataTarget::WriteVirtual-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.WriteVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::WriteVirtual
helpviewer_keywords:
- ICLRDataTarget::WriteVirtual method [.NET Framework debugging]
- WriteVirtual method [.NET Framework debugging]
ms.assetid: d627e8b7-a605-40ac-b9bb-da9a3f1b66d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a0beb9a0b1ef2db6ff32fee1b55b3478794509a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698056"
---
# <a name="iclrdatatargetwritevirtual-method"></a><span data-ttu-id="776e2-102">ICLRDataTarget::WriteVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="776e2-102">ICLRDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="776e2-103">Schreibt Daten aus dem angegebenen Puffer an die Adresse des angegebenen virtuellen Speicher an.</span><span class="sxs-lookup"><span data-stu-id="776e2-103">Writes data from the specified buffer to the specified virtual memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="776e2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="776e2-104">Syntax</span></span>  
  
```  
HRESULT WriteVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [in, size_is(bytesRequested)]   
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesWritten  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="776e2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="776e2-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="776e2-106">[in] Eine CLRDATA_ADDRESS, speichert die Adresse des virtuellen Arbeitsspeichers.</span><span class="sxs-lookup"><span data-stu-id="776e2-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="776e2-107">[in] Ein Zeiger auf einen Puffer, der den Datenspeicher geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="776e2-107">[in] A pointer to a buffer that stores the data to be written.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="776e2-108">[in] Die Anzahl der zu schreibenden Bytes.</span><span class="sxs-lookup"><span data-stu-id="776e2-108">[in] The number of bytes to be written.</span></span>  
  
 `bytesWritten`  
 <span data-ttu-id="776e2-109">[out] Ein Zeiger auf die tatsächliche Anzahl der Bytes, die geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="776e2-109">[out] A pointer to the actual number of bytes that were written.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="776e2-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="776e2-110">Requirements</span></span>  
 <span data-ttu-id="776e2-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="776e2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="776e2-112">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="776e2-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="776e2-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="776e2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="776e2-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="776e2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="776e2-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="776e2-115">See also</span></span>

- [<span data-ttu-id="776e2-116">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="776e2-116">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
