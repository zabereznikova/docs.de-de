---
title: ISymUnmanagedVariable::GetSignature-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable.GetSignature
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetSignature method [.NET Framework debugging]
ms.assetid: 78c1ba28-a410-4360-805c-23a95408964a
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ee403a5f92ba4eb88eca880d9bf2f858b52d4f05
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedvariablegetsignature-method"></a><span data-ttu-id="7cfb9-102">ISymUnmanagedVariable::GetSignature-Methode</span><span class="sxs-lookup"><span data-stu-id="7cfb9-102">ISymUnmanagedVariable::GetSignature Method</span></span>
<span data-ttu-id="7cfb9-103">Ruft die Signatur dieser Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="7cfb9-103">Gets the signature of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cfb9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7cfb9-104">Syntax</span></span>  
  
```  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7cfb9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7cfb9-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="7cfb9-106">[in] Die Länge des Puffers verweist die `sig` Parameter.</span><span class="sxs-lookup"><span data-stu-id="7cfb9-106">[in] The length of the buffer pointed to by the `sig` parameter.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="7cfb9-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe Puffers in Zeichen, die benötigt, damit die Signatur enthalten.</span><span class="sxs-lookup"><span data-stu-id="7cfb9-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="7cfb9-108">[out] Der Puffer, in dem die Signatur gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7cfb9-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7cfb9-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7cfb9-109">Return Value</span></span>  
 <span data-ttu-id="7cfb9-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="7cfb9-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cfb9-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7cfb9-111">Requirements</span></span>  
 <span data-ttu-id="7cfb9-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7cfb9-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cfb9-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7cfb9-113">See Also</span></span>  
 [<span data-ttu-id="7cfb9-114">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7cfb9-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
