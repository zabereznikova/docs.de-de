---
title: ISymUnmanagedWriter::DefineConstant-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineConstant
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineConstant
helpviewer_keywords:
- DefineConstant method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineConstant method [.NET Framework debugging]
ms.assetid: 9e986986-2223-4d5f-b040-85d716146924
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0c7cf800dafa9f3e213a012f49c73d51c78e7074
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427404"
---
# <a name="isymunmanagedwriterdefineconstant-method"></a><span data-ttu-id="e164d-102">ISymUnmanagedWriter::DefineConstant-Methode</span><span class="sxs-lookup"><span data-stu-id="e164d-102">ISymUnmanagedWriter::DefineConstant Method</span></span>
<span data-ttu-id="e164d-103">Definiert einen Namen für einen konstanten Wert.</span><span class="sxs-lookup"><span data-stu-id="e164d-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e164d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e164d-104">Syntax</span></span>  
  
```  
HRESULT DefineConstant(  
    [in] const WCHAR *name,  
    [in] VARIANT value,  
    [in] ULONG32 cSig,  
    [in, size_is(cSig)] unsigned char signature[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e164d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e164d-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="e164d-106">[in] Ein Zeiger auf eine `WCHAR` , der den Namen den Konstanten definiert.</span><span class="sxs-lookup"><span data-stu-id="e164d-106">[in] A pointer to a `WCHAR` that defines the constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="e164d-107">[in] Der Wert der Konstante.</span><span class="sxs-lookup"><span data-stu-id="e164d-107">[in] The value of the constant.</span></span>  
  
 `cSig`  
 <span data-ttu-id="e164d-108">[in] Die Größe des `signature`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="e164d-108">[in] The size of the `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="e164d-109">[in] Die Typsignatur für die Konstante.</span><span class="sxs-lookup"><span data-stu-id="e164d-109">[in] The type signature for the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e164d-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e164d-110">Return Value</span></span>  
 <span data-ttu-id="e164d-111">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="e164d-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e164d-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e164d-112">Requirements</span></span>  
 <span data-ttu-id="e164d-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e164d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e164d-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e164d-114">See Also</span></span>  
 [<span data-ttu-id="e164d-115">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e164d-115">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="e164d-116">DefineConstant2-Methode</span><span class="sxs-lookup"><span data-stu-id="e164d-116">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)
