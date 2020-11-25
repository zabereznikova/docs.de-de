---
title: ISymUnmanagedMethod::GetParameters-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetParameters
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetParameters
helpviewer_keywords:
- ISymUnmanagedMethod::GetParameters method [.NET Framework debugging]
- GetParameters method [.NET Framework debugging]
ms.assetid: 3a8074f1-facc-4a3f-bb9b-d6574fc2fc74
topic_type:
- apiref
ms.openlocfilehash: c66fd810ae4976bc0b5e04572b899465cebe4bbb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699507"
---
# <a name="isymunmanagedmethodgetparameters-method"></a><span data-ttu-id="cc477-102">ISymUnmanagedMethod::GetParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="cc477-102">ISymUnmanagedMethod::GetParameters Method</span></span>

<span data-ttu-id="cc477-103">Ruft die Parameter für diese Methode ab.</span><span class="sxs-lookup"><span data-stu-id="cc477-103">Gets the parameters for this method.</span></span> <span data-ttu-id="cc477-104">Die Parameter werden in der Reihenfolge zurückgegeben, in der Sie in der Signatur der Methode definiert sind.</span><span class="sxs-lookup"><span data-stu-id="cc477-104">The parameters are returned in the order in which they are defined within the method's signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc477-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cc477-105">Syntax</span></span>  
  
```cpp  
HRESULT GetParameters(  
    [in]  ULONG32  cParams,  
    [out] ULONG32  *pcParams,  
    [out, size_is(cParams),  
        length_is(*pcParams)] ISymUnmanagedVariable*  params[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc477-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="cc477-106">Parameters</span></span>  

 `cParams`  
 <span data-ttu-id="cc477-107">[in] Die Größe des `params`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="cc477-107">[in] The size of the `params` array.</span></span>  
  
 `pcParams`  
 <span data-ttu-id="cc477-108">in Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers empfängt, der die Parameter enthalten muss.</span><span class="sxs-lookup"><span data-stu-id="cc477-108">[in] A pointer to a `ULONG32` that receives the size of the buffer that is required to contain the parameters.</span></span>  
  
 `params`  
 <span data-ttu-id="cc477-109">vorgenommen Ein Zeiger auf den Puffer, der die Parameter empfängt.</span><span class="sxs-lookup"><span data-stu-id="cc477-109">[out] A pointer to the buffer that receives the parameters.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc477-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cc477-110">Return Value</span></span>  

 <span data-ttu-id="cc477-111">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="cc477-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc477-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cc477-112">Requirements</span></span>  

 <span data-ttu-id="cc477-113">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="cc477-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc477-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cc477-114">See also</span></span>

- [<span data-ttu-id="cc477-115">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cc477-115">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
