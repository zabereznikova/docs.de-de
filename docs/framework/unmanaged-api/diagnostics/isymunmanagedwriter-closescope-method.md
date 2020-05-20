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
ms.openlocfilehash: 4d8790dc68bc063deed4c58ba0df8e9ea258b9d7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610079"
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="30a89-102">ISymUnmanagedWriter::CloseScope-Methode</span><span class="sxs-lookup"><span data-stu-id="30a89-102">ISymUnmanagedWriter::CloseScope Method</span></span>
<span data-ttu-id="30a89-103">Schließt den aktuellen lexikalischen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="30a89-103">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30a89-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="30a89-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30a89-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="30a89-105">Parameters</span></span>  
 `endOffset`  
 <span data-ttu-id="30a89-106">in Der Offset vom Anfang der Methode des Punkts am Ende der letzten Anweisung im lexikalischen Gültigkeitsbereich (in Bytes).</span><span class="sxs-lookup"><span data-stu-id="30a89-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30a89-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="30a89-107">Return Value</span></span>  
 <span data-ttu-id="30a89-108">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="30a89-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30a89-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="30a89-109">Remarks</span></span>  
 <span data-ttu-id="30a89-110">Nachdem ein Bereich geschlossen wurde, können darin keine weiteren Variablen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="30a89-110">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="30a89-111">[ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) gibt einen nicht transparenten Bereichs Bezeichner zurück, der mit [ISymUnmanagedWriter:: SetScopeRange](isymunmanagedwriter-setscoperange-method.md) verwendet werden kann, um den Start-und Endoffset eines Bereichs zu einem späteren Zeitpunkt zu definieren.</span><span class="sxs-lookup"><span data-stu-id="30a89-111">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="30a89-112">In diesem Fall werden die an `ISymUnmanagedWriter::OpenScope` und `ISymUnmanagedWriter::CloseScope` übergebenen Offsets ignoriert.</span><span class="sxs-lookup"><span data-stu-id="30a89-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="30a89-113">Bereichs Bezeichner sind nur in der aktuellen Methode gültig.</span><span class="sxs-lookup"><span data-stu-id="30a89-113">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30a89-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="30a89-114">Requirements</span></span>  
 <span data-ttu-id="30a89-115">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="30a89-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30a89-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30a89-116">See also</span></span>

- [<span data-ttu-id="30a89-117">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="30a89-117">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
