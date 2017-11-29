---
title: ISymUnmanagedWriter::OpenScope-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.OpenScope
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::OpenScope
helpviewer_keywords:
- OpenScope method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::OpenScope method [.NET Framework debugging]
ms.assetid: dbea0644-3873-4329-90b8-624163e87467
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f56bc14b096b5086db1fc8d046ed699559381fb0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriteropenscope-method"></a><span data-ttu-id="52a21-102">ISymUnmanagedWriter::OpenScope-Methode</span><span class="sxs-lookup"><span data-stu-id="52a21-102">ISymUnmanagedWriter::OpenScope Method</span></span>
<span data-ttu-id="52a21-103">Öffnet einen neuen lexikalischen Gültigkeitsbereich in der aktuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="52a21-103">Opens a new lexical scope in the current method.</span></span> <span data-ttu-id="52a21-104">Der Bereich wird der neue aktuelle Bereich und wird auf einen Stapel von Bereichen abgelegt.</span><span class="sxs-lookup"><span data-stu-id="52a21-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="52a21-105">Bereiche müssen eine Hierarchie zu bilden.</span><span class="sxs-lookup"><span data-stu-id="52a21-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="52a21-106">Gleichgeordnete Elemente dürfen sich nicht überlappen.</span><span class="sxs-lookup"><span data-stu-id="52a21-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52a21-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="52a21-107">Syntax</span></span>  
  
```  
HRESULT OpenScope(  
    [in] ULONG32 startOffset,  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="52a21-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="52a21-108">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="52a21-109">[in] Der Offset der ersten Anweisung im lexikalischen Gültigkeitsbereich, in Bytes vom Anfang der Methode.</span><span class="sxs-lookup"><span data-stu-id="52a21-109">[in] The offset of the first instruction in the lexical scope, in bytes, from the beginning of the method.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="52a21-110">[out] Ein Zeiger auf eine `ULONG32` , empfängt der Bereichsbezeichner.</span><span class="sxs-lookup"><span data-stu-id="52a21-110">[out] A pointer to a `ULONG32` that receives the scope identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52a21-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="52a21-111">Return Value</span></span>  
 <span data-ttu-id="52a21-112">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="52a21-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52a21-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="52a21-113">Remarks</span></span>  
 <span data-ttu-id="52a21-114">`ISymUnmanagedWriter::OpenScope`Gibt einen nicht transparenter Bezeichner, die mit verwendet werden kann [ISymUnmanagedWriter:: SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) zum Definieren eines Bereichs den Anfangs- und Endoffset zu einem späteren Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="52a21-114">`ISymUnmanagedWriter::OpenScope` returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="52a21-115">In diesem Fall das an die Offsets `ISymUnmanagedWriter::OpenScope` und [ISymUnmanagedWriter:: CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="52a21-115">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="52a21-116">Bereichsbezeichnern sind nur in der aktuellen Methode gültig.</span><span class="sxs-lookup"><span data-stu-id="52a21-116">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52a21-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="52a21-117">Requirements</span></span>  
 <span data-ttu-id="52a21-118">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="52a21-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52a21-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52a21-119">See Also</span></span>  
 [<span data-ttu-id="52a21-120">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="52a21-120">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
