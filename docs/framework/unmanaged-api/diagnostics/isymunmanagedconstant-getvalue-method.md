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
ms.openlocfilehash: 8e20d2e0f3d5cb6dc7444c8e78665b6c8b82d2de
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441473"
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="55e4e-102">ISymUnmanagedConstant::GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="55e4e-102">ISymUnmanagedConstant::GetValue Method</span></span>
<span data-ttu-id="55e4e-103"> Ruft den Wert der Konstanten ab.</span><span class="sxs-lookup"><span data-stu-id="55e4e-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55e4e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="55e4e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55e4e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="55e4e-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="55e4e-106">vorgenommen Ein Zeiger auf eine Variable, die den Wert empfängt.</span><span class="sxs-lookup"><span data-stu-id="55e4e-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="55e4e-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="55e4e-107">Return Value</span></span>  
 <span data-ttu-id="55e4e-108">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="55e4e-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55e4e-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="55e4e-109">Requirements</span></span>  
 <span data-ttu-id="55e4e-110">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="55e4e-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55e4e-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55e4e-111">See also</span></span>

- [<span data-ttu-id="55e4e-112">ISymUnmanagedConstant-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="55e4e-112">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)
- [<span data-ttu-id="55e4e-113">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="55e4e-113">GetName Method</span></span>](isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="55e4e-114">GetSignature-Methode</span><span class="sxs-lookup"><span data-stu-id="55e4e-114">GetSignature Method</span></span>](isymunmanagedconstant-getsignature-method.md)
