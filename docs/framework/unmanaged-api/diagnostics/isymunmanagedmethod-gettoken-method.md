---
title: ISymUnmanagedMethod::GetToken-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetToken
helpviewer_keywords:
- ISymUnmanagedMethod::GetToken method [.NET Framework debugging]
- GetToken method, ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: 4effbe95-c36e-4a45-8b2a-ee21339415fb
topic_type:
- apiref
ms.openlocfilehash: 76134a2447cbc40b5c97304540d9907648bc89e8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719917"
---
# <a name="isymunmanagedmethodgettoken-method"></a><span data-ttu-id="d936d-102">ISymUnmanagedMethod::GetToken-Methode</span><span class="sxs-lookup"><span data-stu-id="d936d-102">ISymUnmanagedMethod::GetToken Method</span></span>

<span data-ttu-id="d936d-103">Gibt das Metadatentoken für diese Methode zurück.</span><span class="sxs-lookup"><span data-stu-id="d936d-103">Returns the metadata token for this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d936d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d936d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
   [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d936d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d936d-105">Parameters</span></span>  

 `pToken`  
 <span data-ttu-id="d936d-106">vorgenommen Ein Zeiger auf einen `mdMethodDef` , der die Größe des Puffers, der die Metadaten enthalten muss, in Zeichen empfängt.</span><span class="sxs-lookup"><span data-stu-id="d936d-106">[out] A pointer to a `mdMethodDef` that receives the size, in characters, of the buffer required to contain the metadata.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d936d-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d936d-107">Return Value</span></span>  

 <span data-ttu-id="d936d-108">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="d936d-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d936d-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d936d-109">Requirements</span></span>  

 <span data-ttu-id="d936d-110">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="d936d-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d936d-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d936d-111">See also</span></span>

- [<span data-ttu-id="d936d-112">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d936d-112">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
