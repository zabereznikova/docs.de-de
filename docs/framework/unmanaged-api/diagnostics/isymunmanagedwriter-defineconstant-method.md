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
ms.openlocfilehash: 7f470dbe4ef2ef0d5f2204ccbdd5fb64730f9a2c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159756"
---
# <a name="isymunmanagedwriterdefineconstant-method"></a><span data-ttu-id="9394b-102">ISymUnmanagedWriter::DefineConstant-Methode</span><span class="sxs-lookup"><span data-stu-id="9394b-102">ISymUnmanagedWriter::DefineConstant Method</span></span>
<span data-ttu-id="9394b-103">Definiert einen Namen für einen konstanten Wert.</span><span class="sxs-lookup"><span data-stu-id="9394b-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9394b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9394b-104">Syntax</span></span>  
  
```  
HRESULT DefineConstant(  
    [in] const WCHAR *name,  
    [in] VARIANT value,  
    [in] ULONG32 cSig,  
    [in, size_is(cSig)] unsigned char signature[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9394b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9394b-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="9394b-106">[in] Ein Zeiger auf eine `WCHAR` , die den Namen den Konstanten definiert.</span><span class="sxs-lookup"><span data-stu-id="9394b-106">[in] A pointer to a `WCHAR` that defines the constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="9394b-107">[in] Der Wert der Konstanten.</span><span class="sxs-lookup"><span data-stu-id="9394b-107">[in] The value of the constant.</span></span>  
  
 `cSig`  
 <span data-ttu-id="9394b-108">[in] Die Größe des `signature`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="9394b-108">[in] The size of the `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="9394b-109">[in] Die Typsignatur für die Konstante.</span><span class="sxs-lookup"><span data-stu-id="9394b-109">[in] The type signature for the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9394b-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9394b-110">Return Value</span></span>  
 <span data-ttu-id="9394b-111">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="9394b-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9394b-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9394b-112">Requirements</span></span>  
 <span data-ttu-id="9394b-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9394b-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9394b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9394b-114">See also</span></span>

- [<span data-ttu-id="9394b-115">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9394b-115">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="9394b-116">DefineConstant2-Methode</span><span class="sxs-lookup"><span data-stu-id="9394b-116">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)
