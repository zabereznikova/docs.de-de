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
ms.openlocfilehash: e2e911fb1d737ebb6b2106c89ac11335788ace4f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501728"
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="5d4e5-102">ISymUnmanagedWriter::CloseScope-Methode</span><span class="sxs-lookup"><span data-stu-id="5d4e5-102">ISymUnmanagedWriter::CloseScope Method</span></span>
<span data-ttu-id="5d4e5-103">Schließt den aktuellen lexikalischen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="5d4e5-103">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d4e5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d4e5-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d4e5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5d4e5-105">Parameters</span></span>  
 `endOffset`  
 <span data-ttu-id="5d4e5-106">in Der Offset vom Anfang der Methode des Punkts am Ende der letzten Anweisung im lexikalischen Gültigkeitsbereich (in Bytes).</span><span class="sxs-lookup"><span data-stu-id="5d4e5-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d4e5-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5d4e5-107">Return Value</span></span>  
 <span data-ttu-id="5d4e5-108">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="5d4e5-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d4e5-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5d4e5-109">Remarks</span></span>  
 <span data-ttu-id="5d4e5-110">Nachdem ein Bereich geschlossen wurde, können darin keine weiteren Variablen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="5d4e5-110">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="5d4e5-111">[ISymUnmanagedWriter:: OpenScope](isymunmanagedwriter-openscope-method.md) gibt einen nicht transparenten Bereichs Bezeichner zurück, der mit [ISymUnmanagedWriter:: SetScopeRange](isymunmanagedwriter-setscoperange-method.md) verwendet werden kann, um den Start-und Endoffset eines Bereichs zu einem späteren Zeitpunkt zu definieren.</span><span class="sxs-lookup"><span data-stu-id="5d4e5-111">[ISymUnmanagedWriter::OpenScope](isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="5d4e5-112">In diesem Fall werden die an `ISymUnmanagedWriter::OpenScope` und `ISymUnmanagedWriter::CloseScope` übergebenen Offsets ignoriert.</span><span class="sxs-lookup"><span data-stu-id="5d4e5-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="5d4e5-113">Bereichs Bezeichner sind nur in der aktuellen Methode gültig.</span><span class="sxs-lookup"><span data-stu-id="5d4e5-113">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d4e5-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5d4e5-114">Requirements</span></span>  
 <span data-ttu-id="5d4e5-115">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="5d4e5-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d4e5-116">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="5d4e5-116">See also</span></span>

- [<span data-ttu-id="5d4e5-117">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5d4e5-117">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
