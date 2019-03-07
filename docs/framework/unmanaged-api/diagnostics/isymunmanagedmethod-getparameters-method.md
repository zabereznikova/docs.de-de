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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4b29faaaceb3006ffa114beb78ba245817c58ee8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494193"
---
# <a name="isymunmanagedmethodgetparameters-method"></a><span data-ttu-id="74d94-102">ISymUnmanagedMethod::GetParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="74d94-102">ISymUnmanagedMethod::GetParameters Method</span></span>
<span data-ttu-id="74d94-103">Ruft die Parameter für diese Methode ab.</span><span class="sxs-lookup"><span data-stu-id="74d94-103">Gets the parameters for this method.</span></span> <span data-ttu-id="74d94-104">Die Parameter werden in der Reihenfolge zurückgegeben, in denen sie in der Signatur der Methode definiert sind.</span><span class="sxs-lookup"><span data-stu-id="74d94-104">The parameters are returned in the order in which they are defined within the method's signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74d94-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="74d94-105">Syntax</span></span>  
  
```  
HRESULT GetParameters(  
    [in]  ULONG32  cParams,  
    [out] ULONG32  *pcParams,  
    [out, size_is(cParams),  
        length_is(*pcParams)] ISymUnmanagedVariable*  params[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74d94-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="74d94-106">Parameters</span></span>  
 `cParams`  
 <span data-ttu-id="74d94-107">[in] Die Größe des `params`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="74d94-107">[in] The size of the `params` array.</span></span>  
  
 `pcParams`  
 <span data-ttu-id="74d94-108">[in] Ein Zeiger auf eine `ULONG32` , empfängt die Größe des Puffers, der erforderlich ist, um die Parameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="74d94-108">[in] A pointer to a `ULONG32` that receives the size of the buffer that is required to contain the parameters.</span></span>  
  
 `params`  
 <span data-ttu-id="74d94-109">[out] Ein Zeiger auf den Puffer, der die Parameter empfängt.</span><span class="sxs-lookup"><span data-stu-id="74d94-109">[out] A pointer to the buffer that receives the parameters.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74d94-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="74d94-110">Return Value</span></span>  
 <span data-ttu-id="74d94-111">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="74d94-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74d94-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="74d94-112">Requirements</span></span>  
 <span data-ttu-id="74d94-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="74d94-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74d94-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74d94-114">See also</span></span>
- [<span data-ttu-id="74d94-115">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="74d94-115">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
