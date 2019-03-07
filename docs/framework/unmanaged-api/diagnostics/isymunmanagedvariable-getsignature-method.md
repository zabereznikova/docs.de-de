---
title: ISymUnmanagedVariable::GetSignature-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetSignature method [.NET Framework debugging]
ms.assetid: 78c1ba28-a410-4360-805c-23a95408964a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0f28d6ec882afb21c3c204e141b1b6d883793004
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499055"
---
# <a name="isymunmanagedvariablegetsignature-method"></a><span data-ttu-id="7a8d0-102">ISymUnmanagedVariable::GetSignature-Methode</span><span class="sxs-lookup"><span data-stu-id="7a8d0-102">ISymUnmanagedVariable::GetSignature Method</span></span>
<span data-ttu-id="7a8d0-103">Ruft die Signatur dieser Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="7a8d0-103">Gets the signature of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a8d0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7a8d0-104">Syntax</span></span>  
  
```  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a8d0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7a8d0-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="7a8d0-106">[in] Die Länge des Puffers verweist die `sig` Parameter.</span><span class="sxs-lookup"><span data-stu-id="7a8d0-106">[in] The length of the buffer pointed to by the `sig` parameter.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="7a8d0-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe des für die Signatur enthalten, die erforderlichen Puffers in Zeichen.</span><span class="sxs-lookup"><span data-stu-id="7a8d0-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="7a8d0-108">[out] Der Puffer, in dem die Signatur gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7a8d0-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7a8d0-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7a8d0-109">Return Value</span></span>  
 <span data-ttu-id="7a8d0-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="7a8d0-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a8d0-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7a8d0-111">Requirements</span></span>  
 <span data-ttu-id="7a8d0-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7a8d0-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a8d0-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a8d0-113">See also</span></span>
- [<span data-ttu-id="7a8d0-114">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7a8d0-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
