---
title: ISymUnmanagedWriter::CloseScope-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 250e58e4153edbee5c327ad46ecde73e94b83584
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468714"
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="3ac04-102">ISymUnmanagedWriter::CloseScope-Methode</span><span class="sxs-lookup"><span data-stu-id="3ac04-102">ISymUnmanagedWriter::CloseScope Method</span></span>
<span data-ttu-id="3ac04-103">Schließt den aktuellen lexikalischen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="3ac04-103">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ac04-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ac04-104">Syntax</span></span>  
  
```  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ac04-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3ac04-105">Parameters</span></span>  
 `endOffset`  
 <span data-ttu-id="3ac04-106">[in] Der Offset vom Anfang der Methode des Punkts am Ende der letzten Anweisung im lexikalischen Gültigkeitsbereich, in Bytes.</span><span class="sxs-lookup"><span data-stu-id="3ac04-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ac04-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3ac04-107">Return Value</span></span>  
 <span data-ttu-id="3ac04-108">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="3ac04-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ac04-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3ac04-109">Remarks</span></span>  
 <span data-ttu-id="3ac04-110">Nachdem Sie ein Bereich geschlossen ist, können keine weitere Variablen darin definiert werden.</span><span class="sxs-lookup"><span data-stu-id="3ac04-110">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="3ac04-111">[ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) gibt einen nicht transparenter Bezeichner, die mit verwendet werden kann [ISymUnmanagedWriter:: SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) um später einen Bereich definieren den Anfangs- und der Endoffset.</span><span class="sxs-lookup"><span data-stu-id="3ac04-111">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="3ac04-112">In diesem Fall werden die an `ISymUnmanagedWriter::OpenScope` und `ISymUnmanagedWriter::CloseScope` übergebenen Offsets ignoriert.</span><span class="sxs-lookup"><span data-stu-id="3ac04-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="3ac04-113">Bereichsbezeichnern sind nur in der aktuellen Methode gültig.</span><span class="sxs-lookup"><span data-stu-id="3ac04-113">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ac04-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3ac04-114">Requirements</span></span>  
 <span data-ttu-id="3ac04-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3ac04-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ac04-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ac04-116">See also</span></span>
- [<span data-ttu-id="3ac04-117">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3ac04-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
