---
title: ISymUnmanagedConstant::GetValue-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetValue
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetValue
helpviewer_keywords:
- GetValue method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetValue method [.NET Framework debugging]
ms.assetid: 0036fc10-e768-47a8-b9cf-bf47faf8d194
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 75cc16f44ddf29b161c758718b697cc2aaba8e08
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940022"
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="3f1f2-102">ISymUnmanagedConstant::GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="3f1f2-102">ISymUnmanagedConstant::GetValue Method</span></span>
<span data-ttu-id="3f1f2-103">Ruft den Wert der Konstanten.</span><span class="sxs-lookup"><span data-stu-id="3f1f2-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f1f2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3f1f2-104">Syntax</span></span>  
  
```  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f1f2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3f1f2-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="3f1f2-106">[out] Ein Zeiger auf eine Variable, die den Wert empfängt.</span><span class="sxs-lookup"><span data-stu-id="3f1f2-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f1f2-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3f1f2-107">Return Value</span></span>  
 <span data-ttu-id="3f1f2-108">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="3f1f2-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f1f2-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3f1f2-109">Requirements</span></span>  
 <span data-ttu-id="3f1f2-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3f1f2-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f1f2-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f1f2-111">See also</span></span>

- [<span data-ttu-id="3f1f2-112">ISymUnmanagedConstant-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3f1f2-112">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="3f1f2-113">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="3f1f2-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="3f1f2-114">GetSignature-Methode</span><span class="sxs-lookup"><span data-stu-id="3f1f2-114">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
