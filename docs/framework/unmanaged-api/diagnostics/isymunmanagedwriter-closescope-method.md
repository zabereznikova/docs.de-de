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
ms.openlocfilehash: 9ab30e1f80be71b42a131afe68e38f0b2731ae60
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212946"
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="fdfdb-102">ISymUnmanagedWriter::CloseScope-Methode</span><span class="sxs-lookup"><span data-stu-id="fdfdb-102">ISymUnmanagedWriter::CloseScope Method</span></span>
<span data-ttu-id="fdfdb-103">Schließt den aktuellen lexikalischen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="fdfdb-103">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdfdb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fdfdb-104">Syntax</span></span>  
  
```  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fdfdb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fdfdb-105">Parameters</span></span>  
 `endOffset`  
 <span data-ttu-id="fdfdb-106">[in] Der Offset vom Anfang der Methode des Punkts am Ende der letzten Anweisung im lexikalischen Gültigkeitsbereich, in Bytes.</span><span class="sxs-lookup"><span data-stu-id="fdfdb-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fdfdb-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fdfdb-107">Return Value</span></span>  
 <span data-ttu-id="fdfdb-108">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="fdfdb-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fdfdb-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fdfdb-109">Remarks</span></span>  
 <span data-ttu-id="fdfdb-110">Nachdem Sie ein Bereich geschlossen ist, können keine weitere Variablen darin definiert werden.</span><span class="sxs-lookup"><span data-stu-id="fdfdb-110">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="fdfdb-111">[ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) gibt einen nicht transparenter Bezeichner, die mit verwendet werden kann [ISymUnmanagedWriter:: SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) um später einen Bereich definieren den Anfangs- und der Endoffset.</span><span class="sxs-lookup"><span data-stu-id="fdfdb-111">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="fdfdb-112">In diesem Fall werden die an `ISymUnmanagedWriter::OpenScope` und `ISymUnmanagedWriter::CloseScope` übergebenen Offsets ignoriert.</span><span class="sxs-lookup"><span data-stu-id="fdfdb-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="fdfdb-113">Bereichsbezeichnern sind nur in der aktuellen Methode gültig.</span><span class="sxs-lookup"><span data-stu-id="fdfdb-113">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdfdb-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fdfdb-114">Requirements</span></span>  
 <span data-ttu-id="fdfdb-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fdfdb-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdfdb-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fdfdb-116">See also</span></span>

- [<span data-ttu-id="fdfdb-117">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fdfdb-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
