---
title: ISymUnmanagedConstant::GetSignature-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedConstant.GetSignature
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedConstant::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetSignature method [.NET Framework debugging]
ms.assetid: 3eb41151-a228-43e3-ba8f-e6dd3ceb8542
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 10bdf7b8b83b56ff856d966d2764ed04e06090aa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedconstantgetsignature-method"></a><span data-ttu-id="e99bf-102">ISymUnmanagedConstant::GetSignature-Methode</span><span class="sxs-lookup"><span data-stu-id="e99bf-102">ISymUnmanagedConstant::GetSignature Method</span></span>
<span data-ttu-id="e99bf-103">Ruft die Signatur der Konstanten ab.</span><span class="sxs-lookup"><span data-stu-id="e99bf-103">Gets the signature of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e99bf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e99bf-104">Syntax</span></span>  
  
```  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e99bf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e99bf-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="e99bf-106">[in] Die Länge des Puffers, der `pcSig` -Parameter zeigt.</span><span class="sxs-lookup"><span data-stu-id="e99bf-106">[in] The length of the buffer that the `pcSig` parameter points to.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="e99bf-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe Puffers in Zeichen, die benötigt, damit die Signatur enthalten.</span><span class="sxs-lookup"><span data-stu-id="e99bf-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="e99bf-108">[out] Der Puffer, in dem die Signatur gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e99bf-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e99bf-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e99bf-109">Return Value</span></span>  
 <span data-ttu-id="e99bf-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="e99bf-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e99bf-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e99bf-111">Requirements</span></span>  
 <span data-ttu-id="e99bf-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e99bf-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e99bf-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e99bf-113">See Also</span></span>  
 [<span data-ttu-id="e99bf-114">ISymUnmanagedConstant-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e99bf-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 [<span data-ttu-id="e99bf-115">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="e99bf-115">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)  
 [<span data-ttu-id="e99bf-116">GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="e99bf-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
