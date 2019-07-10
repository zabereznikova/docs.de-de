---
title: ISymUnmanagedWriter2::DefineConstant2-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineConstant2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineConstant2
helpviewer_keywords:
- DefineConstant2 method [.NET Framework debugging]
- ISymUnmanagedWriter2::DefineConstant2 method [.NET Framework debugging]
ms.assetid: dd2bc956-7dbe-49fc-a646-daa0d267f2df
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c194cea21901015153626dc5aead49ed1b2c3df7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755112"
---
# <a name="isymunmanagedwriter2defineconstant2-method"></a><span data-ttu-id="8b54d-102">ISymUnmanagedWriter2::DefineConstant2-Methode</span><span class="sxs-lookup"><span data-stu-id="8b54d-102">ISymUnmanagedWriter2::DefineConstant2 Method</span></span>
<span data-ttu-id="8b54d-103">Definiert einen Namen für einen konstanten Wert.</span><span class="sxs-lookup"><span data-stu-id="8b54d-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b54d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8b54d-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineConstant2(  
    [in] const WCHAR  *name,  
    [in] VARIANT      value,  
    [in] mdSignature  sigToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b54d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8b54d-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="8b54d-106">[in] Den Namen der Konstante.</span><span class="sxs-lookup"><span data-stu-id="8b54d-106">[in] The constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="8b54d-107">[in] Der Wert der Konstanten.</span><span class="sxs-lookup"><span data-stu-id="8b54d-107">[in] The value of the constant.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="8b54d-108">[in] Das Metadatentoken der Konstante.</span><span class="sxs-lookup"><span data-stu-id="8b54d-108">[in] The metadata token of the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8b54d-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8b54d-109">Return Value</span></span>  
 <span data-ttu-id="8b54d-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="8b54d-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b54d-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8b54d-111">Requirements</span></span>  
 <span data-ttu-id="8b54d-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8b54d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b54d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b54d-113">See also</span></span>

- [<span data-ttu-id="8b54d-114">ISymUnmanagedWriter2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8b54d-114">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="8b54d-115">DefineConstant-Methode</span><span class="sxs-lookup"><span data-stu-id="8b54d-115">DefineConstant Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineconstant-method.md)
