---
title: ICLRDataTarget::Request-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.Request
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::Request
helpviewer_keywords:
- ICLRDataTarget::Request method [.NET Framework debugging]
- Request method [.NET Framework debugging]
ms.assetid: 4723bd1c-eddb-4ed2-897a-010024a47e01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5f6926d66a438cfc4fd97d7120e359b737212dde
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738632"
---
# <a name="iclrdatatargetrequest-method"></a><span data-ttu-id="5c9a2-102">ICLRDataTarget::Request-Methode</span><span class="sxs-lookup"><span data-stu-id="5c9a2-102">ICLRDataTarget::Request Method</span></span>
<span data-ttu-id="5c9a2-103">Aufgerufen von der common Language Runtime (CLR) Datenzugriffsdiensten der zum Anfordern eines Vorgangs, wie durch die Implementierung definiert.</span><span class="sxs-lookup"><span data-stu-id="5c9a2-103">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c9a2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5c9a2-104">Syntax</span></span>  
  
```cpp  
HRESULT Request (  
    [in] ULONG32            reqCode,  
    [in] ULONG32            inBufferSize,  
    [in, size_is(inBufferSize)]   
        BYTE                *inBuffer,  
    [in] ULONG32            outBufferSize,  
    [out, size_is(outBufferSize)]   
        BYTE                *outBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c9a2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5c9a2-105">Parameters</span></span>  
 `reqCode`  
 <span data-ttu-id="5c9a2-106">[in] Vom Benutzer definiert.</span><span class="sxs-lookup"><span data-stu-id="5c9a2-106">[in] User-defined.</span></span>  
  
 `inBufferSize`  
 <span data-ttu-id="5c9a2-107">[in] Die Größe des Eingabepuffers, die für die eingehende Anforderung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5c9a2-107">[in] The size of the input buffer, which is used for the incoming request.</span></span>  
  
 `inBuffer`  
 <span data-ttu-id="5c9a2-108">[in] Ein Puffer, der die Anforderung enthält.</span><span class="sxs-lookup"><span data-stu-id="5c9a2-108">[in] A buffer containing the request.</span></span>  
  
 `outBufferSize`  
 <span data-ttu-id="5c9a2-109">[in] Die Größe des Ausgabepuffers, die für die Antwort verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5c9a2-109">[in] The size of the output buffer, which is used for the response.</span></span>  
  
 `outBuffer`  
 <span data-ttu-id="5c9a2-110">[out] Ein Puffer mit der Antwort.</span><span class="sxs-lookup"><span data-stu-id="5c9a2-110">[out] A Buffer containing the response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c9a2-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5c9a2-111">Remarks</span></span>  
 <span data-ttu-id="5c9a2-112">Die `Request` Methode ermöglicht das Hinzufügen nicht angegebener benutzerdefinierter Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="5c9a2-112">The `Request` method facilitates the addition of unspecified custom operations.</span></span> <span data-ttu-id="5c9a2-113">Diese Methode, also bereitstellt Erweiterbarkeit ohne Revision der Definition der Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="5c9a2-113">That is, this method provides extensibility without requiring revision of the interface definition.</span></span>  
  
 <span data-ttu-id="5c9a2-114">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="5c9a2-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c9a2-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5c9a2-115">Requirements</span></span>  
 <span data-ttu-id="5c9a2-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c9a2-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c9a2-117">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="5c9a2-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="5c9a2-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c9a2-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c9a2-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c9a2-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c9a2-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c9a2-120">See also</span></span>

- [<span data-ttu-id="5c9a2-121">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5c9a2-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
