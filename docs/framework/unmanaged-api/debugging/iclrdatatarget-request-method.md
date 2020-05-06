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
ms.openlocfilehash: b913affb4728dc80ba67438384cbeac87265f76d
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860543"
---
# <a name="iclrdatatargetrequest-method"></a><span data-ttu-id="14dc4-102">ICLRDataTarget::Request-Methode</span><span class="sxs-lookup"><span data-stu-id="14dc4-102">ICLRDataTarget::Request Method</span></span>
<span data-ttu-id="14dc4-103">Wird von den Common Language Runtime (CLR)-Datenzugriffs Diensten aufgerufen, um einen Vorgang anzufordern, wie in der-Implementierung definiert.</span><span class="sxs-lookup"><span data-stu-id="14dc4-103">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14dc4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="14dc4-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="14dc4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="14dc4-105">Parameters</span></span>  
 `reqCode`  
 <span data-ttu-id="14dc4-106">in Benutzer definiert.</span><span class="sxs-lookup"><span data-stu-id="14dc4-106">[in] User-defined.</span></span>  
  
 `inBufferSize`  
 <span data-ttu-id="14dc4-107">in Die Größe des Eingabe Puffers, der für die eingehende Anforderung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="14dc4-107">[in] The size of the input buffer, which is used for the incoming request.</span></span>  
  
 `inBuffer`  
 <span data-ttu-id="14dc4-108">in Ein Puffer, der die Anforderung enthält.</span><span class="sxs-lookup"><span data-stu-id="14dc4-108">[in] A buffer containing the request.</span></span>  
  
 `outBufferSize`  
 <span data-ttu-id="14dc4-109">in Die Größe des Ausgabepuffers, der für die Antwort verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="14dc4-109">[in] The size of the output buffer, which is used for the response.</span></span>  
  
 `outBuffer`  
 <span data-ttu-id="14dc4-110">vorgenommen Ein Puffer, der die Antwort enthält.</span><span class="sxs-lookup"><span data-stu-id="14dc4-110">[out] A Buffer containing the response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14dc4-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="14dc4-111">Remarks</span></span>  
 <span data-ttu-id="14dc4-112">Die `Request` -Methode vereinfacht das Hinzufügen von nicht angegebenen benutzerdefinierten Vorgängen.</span><span class="sxs-lookup"><span data-stu-id="14dc4-112">The `Request` method facilitates the addition of unspecified custom operations.</span></span> <span data-ttu-id="14dc4-113">Das heißt, diese Methode bietet Erweiterbarkeit, ohne dass eine Revision der Schnittstellen Definition erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="14dc4-113">That is, this method provides extensibility without requiring revision of the interface definition.</span></span>  
  
 <span data-ttu-id="14dc4-114">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="14dc4-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14dc4-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="14dc4-115">Requirements</span></span>  
 <span data-ttu-id="14dc4-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14dc4-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14dc4-117">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="14dc4-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="14dc4-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14dc4-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14dc4-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14dc4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14dc4-120">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="14dc4-120">See also</span></span>

- [<span data-ttu-id="14dc4-121">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="14dc4-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
