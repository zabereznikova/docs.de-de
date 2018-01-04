---
title: ISymUnmanagedWriter::DefineConstant-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.DefineConstant
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::DefineConstant
helpviewer_keywords:
- DefineConstant method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineConstant method [.NET Framework debugging]
ms.assetid: 9e986986-2223-4d5f-b040-85d716146924
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9b22b0d9c9de27ba9950a0501193bc682586bfbc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterdefineconstant-method"></a><span data-ttu-id="1d772-102">ISymUnmanagedWriter::DefineConstant-Methode</span><span class="sxs-lookup"><span data-stu-id="1d772-102">ISymUnmanagedWriter::DefineConstant Method</span></span>
<span data-ttu-id="1d772-103">Definiert einen Namen für einen konstanten Wert.</span><span class="sxs-lookup"><span data-stu-id="1d772-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d772-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1d772-104">Syntax</span></span>  
  
```  
HRESULT DefineConstant(  
    [in] const WCHAR *name,  
    [in] VARIANT value,  
    [in] ULONG32 cSig,  
    [in, size_is(cSig)] unsigned char signature[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1d772-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1d772-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="1d772-106">[in] Ein Zeiger auf eine `WCHAR` , der den Namen den Konstanten definiert.</span><span class="sxs-lookup"><span data-stu-id="1d772-106">[in] A pointer to a `WCHAR` that defines the constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="1d772-107">[in] Der Wert der Konstante.</span><span class="sxs-lookup"><span data-stu-id="1d772-107">[in] The value of the constant.</span></span>  
  
 `cSig`  
 <span data-ttu-id="1d772-108">[in] Die Größe des `signature`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="1d772-108">[in] The size of the `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="1d772-109">[in] Die Typsignatur für die Konstante.</span><span class="sxs-lookup"><span data-stu-id="1d772-109">[in] The type signature for the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d772-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1d772-110">Return Value</span></span>  
 <span data-ttu-id="1d772-111">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="1d772-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d772-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1d772-112">Requirements</span></span>  
 <span data-ttu-id="1d772-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1d772-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d772-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d772-114">See Also</span></span>  
 [<span data-ttu-id="1d772-115">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d772-115">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="1d772-116">DefineConstant2-Methode</span><span class="sxs-lookup"><span data-stu-id="1d772-116">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)
