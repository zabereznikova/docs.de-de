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
ms.openlocfilehash: 0803f0b55f19b779f5b6608a9f8200d2b085b504
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615156"
---
# <a name="isymunmanagedmethodgettoken-method"></a><span data-ttu-id="1c6d1-102">ISymUnmanagedMethod::GetToken-Methode</span><span class="sxs-lookup"><span data-stu-id="1c6d1-102">ISymUnmanagedMethod::GetToken Method</span></span>
<span data-ttu-id="1c6d1-103">Gibt das Metadatentoken für diese Methode zurück.</span><span class="sxs-lookup"><span data-stu-id="1c6d1-103">Returns the metadata token for this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c6d1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1c6d1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
   [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c6d1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1c6d1-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="1c6d1-106">vorgenommen Ein Zeiger auf einen `mdMethodDef` , der die Größe des Puffers, der die Metadaten enthalten muss, in Zeichen empfängt.</span><span class="sxs-lookup"><span data-stu-id="1c6d1-106">[out] A pointer to a `mdMethodDef` that receives the size, in characters, of the buffer required to contain the metadata.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1c6d1-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1c6d1-107">Return Value</span></span>  
 <span data-ttu-id="1c6d1-108">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="1c6d1-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c6d1-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1c6d1-109">Requirements</span></span>  
 <span data-ttu-id="1c6d1-110">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="1c6d1-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c6d1-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c6d1-111">See also</span></span>

- [<span data-ttu-id="1c6d1-112">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1c6d1-112">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
