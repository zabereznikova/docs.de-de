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
ms.openlocfilehash: 791b92c30fc2bf3d506113620b59ba20015e077e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725819"
---
# <a name="isymunmanagedvariablegetsignature-method"></a><span data-ttu-id="bfbc8-102">ISymUnmanagedVariable::GetSignature-Methode</span><span class="sxs-lookup"><span data-stu-id="bfbc8-102">ISymUnmanagedVariable::GetSignature Method</span></span>

<span data-ttu-id="bfbc8-103">Ruft die Signatur dieser Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="bfbc8-103">Gets the signature of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfbc8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bfbc8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bfbc8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bfbc8-105">Parameters</span></span>  

 `cSig`  
 <span data-ttu-id="bfbc8-106">in Die Länge des Puffers, auf den der- `sig` Parameter zeigt.</span><span class="sxs-lookup"><span data-stu-id="bfbc8-106">[in] The length of the buffer pointed to by the `sig` parameter.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="bfbc8-107">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers, der die Signatur enthalten muss, in Zeichen empfängt.</span><span class="sxs-lookup"><span data-stu-id="bfbc8-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="bfbc8-108">vorgenommen Der Puffer, in dem die Signatur gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="bfbc8-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bfbc8-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bfbc8-109">Return Value</span></span>  

 <span data-ttu-id="bfbc8-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="bfbc8-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfbc8-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bfbc8-111">Requirements</span></span>  

 <span data-ttu-id="bfbc8-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="bfbc8-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfbc8-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bfbc8-113">See also</span></span>

- [<span data-ttu-id="bfbc8-114">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bfbc8-114">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
