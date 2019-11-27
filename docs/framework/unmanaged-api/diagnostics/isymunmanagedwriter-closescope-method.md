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
ms.openlocfilehash: 264b4487483ed5439a9809feefcdc1b20af402dc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428077"
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="d409f-102">ISymUnmanagedWriter::CloseScope-Methode</span><span class="sxs-lookup"><span data-stu-id="d409f-102">ISymUnmanagedWriter::CloseScope Method</span></span>
<span data-ttu-id="d409f-103">Schließt den aktuellen lexikalischen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="d409f-103">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d409f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d409f-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d409f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d409f-105">Parameters</span></span>  
 `endOffset`  
 <span data-ttu-id="d409f-106">in Der Offset vom Anfang der Methode des Punkts am Ende der letzten Anweisung im lexikalischen Gültigkeitsbereich (in Bytes).</span><span class="sxs-lookup"><span data-stu-id="d409f-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d409f-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d409f-107">Return Value</span></span>  
 <span data-ttu-id="d409f-108">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="d409f-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d409f-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d409f-109">Remarks</span></span>  
 <span data-ttu-id="d409f-110">Nachdem ein Bereich geschlossen wurde, können darin keine weiteren Variablen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="d409f-110">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="d409f-111">[ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) gibt einen nicht transparenten Bereichs Bezeichner zurück, der mit [ISymUnmanagedWriter:: SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) verwendet werden kann, um den Start-und Endoffset eines Bereichs zu einem späteren Zeitpunkt zu definieren.</span><span class="sxs-lookup"><span data-stu-id="d409f-111">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="d409f-112">In diesem Fall werden die an `ISymUnmanagedWriter::OpenScope` und `ISymUnmanagedWriter::CloseScope` übergebenen Offsets ignoriert.</span><span class="sxs-lookup"><span data-stu-id="d409f-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="d409f-113">Bereichs Bezeichner sind nur in der aktuellen Methode gültig.</span><span class="sxs-lookup"><span data-stu-id="d409f-113">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d409f-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="d409f-114">Requirements</span></span>  
 <span data-ttu-id="d409f-115">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="d409f-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d409f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d409f-116">See also</span></span>

- [<span data-ttu-id="d409f-117">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d409f-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
