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
ms.openlocfilehash: 00be35e9a15349b8bca5f76b948b8477dd240888
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449240"
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="08a01-102">ISymUnmanagedConstant::GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="08a01-102">ISymUnmanagedConstant::GetValue Method</span></span>
<span data-ttu-id="08a01-103">Ruft den Wert der Konstante ab.</span><span class="sxs-lookup"><span data-stu-id="08a01-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08a01-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="08a01-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08a01-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="08a01-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="08a01-106">vorgenommen Ein Zeiger auf eine Variable, die den Wert empfängt.</span><span class="sxs-lookup"><span data-stu-id="08a01-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08a01-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="08a01-107">Return Value</span></span>  
 <span data-ttu-id="08a01-108">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="08a01-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08a01-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="08a01-109">Requirements</span></span>  
 <span data-ttu-id="08a01-110">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="08a01-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08a01-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08a01-111">See also</span></span>

- [<span data-ttu-id="08a01-112">ISymUnmanagedConstant-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08a01-112">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="08a01-113">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="08a01-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="08a01-114">GetSignature-Methode</span><span class="sxs-lookup"><span data-stu-id="08a01-114">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
