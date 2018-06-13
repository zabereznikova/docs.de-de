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
ms.openlocfilehash: e55bc18c7a41e235d1ba6274067c45c26dc7262a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405452"
---
# <a name="iclrdatatargetwritevirtual-method"></a><span data-ttu-id="eb28f-102">ICLRDataTarget::WriteVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="eb28f-102">ICLRDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="eb28f-103">Schreibt Daten aus dem angegebenen Puffer auf die angegebene virtuelle Speicheradresse.</span><span class="sxs-lookup"><span data-stu-id="eb28f-103">Writes data from the specified buffer to the specified virtual memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb28f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb28f-104">Syntax</span></span>  
  
```  
HRESULT WriteVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [in, size_is(bytesRequested)]   
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesWritten  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eb28f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="eb28f-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="eb28f-106">[in] Eine CLRDATA_ADDRESS, die Adresse des virtuellen Arbeitsspeichers speichert.</span><span class="sxs-lookup"><span data-stu-id="eb28f-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="eb28f-107">[in] Ein Zeiger auf einen Puffer, der die zu schreibenden Daten speichert.</span><span class="sxs-lookup"><span data-stu-id="eb28f-107">[in] A pointer to a buffer that stores the data to be written.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="eb28f-108">[in] Die Anzahl der zu schreibenden Bytes.</span><span class="sxs-lookup"><span data-stu-id="eb28f-108">[in] The number of bytes to be written.</span></span>  
  
 `bytesWritten`  
 <span data-ttu-id="eb28f-109">[out] Ein Zeiger auf die tatsächliche Anzahl von Bytes, die geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="eb28f-109">[out] A pointer to the actual number of bytes that were written.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb28f-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eb28f-110">Requirements</span></span>  
 <span data-ttu-id="eb28f-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb28f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb28f-112">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="eb28f-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="eb28f-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb28f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb28f-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb28f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb28f-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb28f-115">See Also</span></span>  
 [<span data-ttu-id="eb28f-116">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eb28f-116">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
