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
ms.openlocfilehash: 3e9bff5be747c4872554a69dd316de8ca9eb9934
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198932"
---
# <a name="isymunmanagedwriter2defineconstant2-method"></a><span data-ttu-id="21670-102">ISymUnmanagedWriter2::DefineConstant2-Methode</span><span class="sxs-lookup"><span data-stu-id="21670-102">ISymUnmanagedWriter2::DefineConstant2 Method</span></span>
<span data-ttu-id="21670-103">Definiert einen Namen für einen konstanten Wert.</span><span class="sxs-lookup"><span data-stu-id="21670-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21670-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="21670-104">Syntax</span></span>  
  
```  
HRESULT DefineConstant2(  
    [in] const WCHAR  *name,  
    [in] VARIANT      value,  
    [in] mdSignature  sigToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21670-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="21670-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="21670-106">[in] Den Namen der Konstante.</span><span class="sxs-lookup"><span data-stu-id="21670-106">[in] The constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="21670-107">[in] Der Wert der Konstanten.</span><span class="sxs-lookup"><span data-stu-id="21670-107">[in] The value of the constant.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="21670-108">[in] Das Metadatentoken der Konstante.</span><span class="sxs-lookup"><span data-stu-id="21670-108">[in] The metadata token of the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="21670-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="21670-109">Return Value</span></span>  
 <span data-ttu-id="21670-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="21670-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21670-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="21670-111">Requirements</span></span>  
 <span data-ttu-id="21670-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="21670-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21670-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21670-113">See also</span></span>

- [<span data-ttu-id="21670-114">ISymUnmanagedWriter2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="21670-114">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="21670-115">DefineConstant-Methode</span><span class="sxs-lookup"><span data-stu-id="21670-115">DefineConstant Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineconstant-method.md)
