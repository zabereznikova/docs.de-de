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
ms.openlocfilehash: 314d9115fdba7d57538e5b24c56863944db517fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedconstantgetsignature-method"></a><span data-ttu-id="75295-102">ISymUnmanagedConstant::GetSignature-Methode</span><span class="sxs-lookup"><span data-stu-id="75295-102">ISymUnmanagedConstant::GetSignature Method</span></span>
<span data-ttu-id="75295-103">Ruft die Signatur der Konstanten ab.</span><span class="sxs-lookup"><span data-stu-id="75295-103">Gets the signature of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75295-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="75295-104">Syntax</span></span>  
  
```  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="75295-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="75295-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="75295-106">[in] Die Länge des Puffers, der `pcSig` -Parameter zeigt.</span><span class="sxs-lookup"><span data-stu-id="75295-106">[in] The length of the buffer that the `pcSig` parameter points to.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="75295-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe Puffers in Zeichen, die benötigt, damit die Signatur enthalten.</span><span class="sxs-lookup"><span data-stu-id="75295-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="75295-108">[out] Der Puffer, in dem die Signatur gespeichert.</span><span class="sxs-lookup"><span data-stu-id="75295-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="75295-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="75295-109">Return Value</span></span>  
 <span data-ttu-id="75295-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="75295-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75295-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="75295-111">Requirements</span></span>  
 <span data-ttu-id="75295-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="75295-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75295-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75295-113">See Also</span></span>  
 [<span data-ttu-id="75295-114">ISymUnmanagedConstant-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="75295-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 [<span data-ttu-id="75295-115">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="75295-115">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)  
 [<span data-ttu-id="75295-116">GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="75295-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
