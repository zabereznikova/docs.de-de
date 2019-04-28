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
ms.openlocfilehash: 3cc616246812bb9643388d8ad57cf84bc387b55e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797500"
---
# <a name="isymunmanagedvariablegetsignature-method"></a><span data-ttu-id="5331f-102">ISymUnmanagedVariable::GetSignature-Methode</span><span class="sxs-lookup"><span data-stu-id="5331f-102">ISymUnmanagedVariable::GetSignature Method</span></span>
<span data-ttu-id="5331f-103">Ruft die Signatur dieser Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="5331f-103">Gets the signature of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5331f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5331f-104">Syntax</span></span>  
  
```  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5331f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5331f-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="5331f-106">[in] Die Länge des Puffers verweist die `sig` Parameter.</span><span class="sxs-lookup"><span data-stu-id="5331f-106">[in] The length of the buffer pointed to by the `sig` parameter.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="5331f-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe des für die Signatur enthalten, die erforderlichen Puffers in Zeichen.</span><span class="sxs-lookup"><span data-stu-id="5331f-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="5331f-108">[out] Der Puffer, in dem die Signatur gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5331f-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5331f-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5331f-109">Return Value</span></span>  
 <span data-ttu-id="5331f-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="5331f-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5331f-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5331f-111">Requirements</span></span>  
 <span data-ttu-id="5331f-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5331f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5331f-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5331f-113">See also</span></span>

- [<span data-ttu-id="5331f-114">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5331f-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
