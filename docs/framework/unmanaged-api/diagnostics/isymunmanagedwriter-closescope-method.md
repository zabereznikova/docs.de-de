---
title: ISymUnmanagedWriter::CloseScope-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedWriter.CloseScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseScope
helpviewer_keywords:
- CloseScope method [.NET Framework debugging]
- ISymUnmanagedWriter::CloseScope method [.NET Framework debugging]
ms.assetid: 6dade525-7770-4cb4-bafd-4bb995ad0d87
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d47be1d220729ed32fcf77a77e611003085c15d6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="d7701-102">ISymUnmanagedWriter::CloseScope-Methode</span><span class="sxs-lookup"><span data-stu-id="d7701-102">ISymUnmanagedWriter::CloseScope Method</span></span>
<span data-ttu-id="d7701-103">Schließt den aktuellen lexikalischen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="d7701-103">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7701-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d7701-104">Syntax</span></span>  
  
```  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d7701-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d7701-105">Parameters</span></span>  
 `endOffset`  
 <span data-ttu-id="d7701-106">[in] Der Offset vom Anfang der Methode von den Punkt am Ende der letzten Anweisung im lexikalischen Gültigkeitsbereich, in Bytes.</span><span class="sxs-lookup"><span data-stu-id="d7701-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7701-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d7701-107">Return Value</span></span>  
 <span data-ttu-id="d7701-108">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="d7701-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7701-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d7701-109">Remarks</span></span>  
 <span data-ttu-id="d7701-110">Nachdem ein Bereich geschlossen wurde, können keine weitere Variablen darin definiert werden.</span><span class="sxs-lookup"><span data-stu-id="d7701-110">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="d7701-111">[ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) gibt einen nicht transparenter Bezeichner, die mit verwendet werden kann [ISymUnmanagedWriter:: SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) zum später definieren eines Bereichs den Anfangs- und der Endoffset.</span><span class="sxs-lookup"><span data-stu-id="d7701-111">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="d7701-112">In diesem Fall werden die an `ISymUnmanagedWriter::OpenScope` und `ISymUnmanagedWriter::CloseScope` übergebenen Offsets ignoriert.</span><span class="sxs-lookup"><span data-stu-id="d7701-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="d7701-113">Bereichsbezeichnern sind nur in der aktuellen Methode gültig.</span><span class="sxs-lookup"><span data-stu-id="d7701-113">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7701-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d7701-114">Requirements</span></span>  
 <span data-ttu-id="d7701-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d7701-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7701-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7701-116">See Also</span></span>  
 [<span data-ttu-id="d7701-117">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d7701-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
