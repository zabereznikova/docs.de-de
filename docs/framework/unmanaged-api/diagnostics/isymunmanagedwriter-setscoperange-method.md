---
title: ISymUnmanagedWriter::SetScopeRange-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetScopeRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetScopeRange
helpviewer_keywords:
- SetScopeRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetScopeRange method [.NET Framework debugging]
ms.assetid: d4d98676-444b-46ca-bfe6-0d827385cd22
topic_type:
- apiref
ms.openlocfilehash: 06dff4847ec3d15f446f1c89219b10eddb8eec4f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683523"
---
# <a name="isymunmanagedwritersetscoperange-method"></a><span data-ttu-id="29867-102">ISymUnmanagedWriter::SetScopeRange-Methode</span><span class="sxs-lookup"><span data-stu-id="29867-102">ISymUnmanagedWriter::SetScopeRange Method</span></span>

<span data-ttu-id="29867-103">Definiert den Offsetbereich für den angegebenen lexikalischen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="29867-103">Defines the offset range for the specified lexical scope.</span></span> <span data-ttu-id="29867-104">Der Gültigkeitsbereich wird zum neuen aktuellen Bereich und wird auf einen Stapel von Bereichen übermittelt.</span><span class="sxs-lookup"><span data-stu-id="29867-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="29867-105">Bereiche müssen eine Hierarchie bilden.</span><span class="sxs-lookup"><span data-stu-id="29867-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="29867-106">Gleich geordnete Elemente dürfen sich nicht überlappen.</span><span class="sxs-lookup"><span data-stu-id="29867-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29867-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="29867-107">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29867-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="29867-108">Parameters</span></span>  

 `scopeId`  
 <span data-ttu-id="29867-109">in Der Bereichs Bezeichner für den Bereich.</span><span class="sxs-lookup"><span data-stu-id="29867-109">[in] The scope identifier for the scope.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="29867-110">in Der Offset (in Bytes) der ersten Anweisung im lexikalischen Gültigkeitsbereich vom Anfang der Methode.</span><span class="sxs-lookup"><span data-stu-id="29867-110">[in] The offset, in bytes, of the first instruction in the lexical scope from the beginning of the method.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="29867-111">in Der Offset (in Bytes) der letzten Anweisung im lexikalischen Gültigkeitsbereich ab dem Anfang der Methode.</span><span class="sxs-lookup"><span data-stu-id="29867-111">[in] The offset, in bytes, of the last instruction in the lexical scope from the beginning of the method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="29867-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="29867-112">Return Value</span></span>  

 <span data-ttu-id="29867-113">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="29867-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29867-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="29867-114">Remarks</span></span>  

 <span data-ttu-id="29867-115">[ISymUnmanagedWriter:: OpenScope](isymunmanagedwriter-openscope-method.md) gibt einen nicht transparenten Bereichs Bezeichner zurück, der mit verwendet werden kann `ISymUnmanagedWriter::SetScopeRange` , um den Start-und Endoffset eines Bereichs zu einem späteren Zeitpunkt zu definieren.</span><span class="sxs-lookup"><span data-stu-id="29867-115">[ISymUnmanagedWriter::OpenScope](isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with `ISymUnmanagedWriter::SetScopeRange` to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="29867-116">In diesem Fall werden die an `ISymUnmanagedWriter::OpenScope` -und [ISymUnmanagedWriter:: CloseScope](isymunmanagedwriter-closescope-method.md) übergebenen Offsets ignoriert.</span><span class="sxs-lookup"><span data-stu-id="29867-116">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="29867-117">Bereichs Bezeichner sind nur in der aktuellen Methode gültig.</span><span class="sxs-lookup"><span data-stu-id="29867-117">Scope identifiers are only valid in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29867-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="29867-118">Requirements</span></span>  

 <span data-ttu-id="29867-119">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="29867-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29867-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="29867-120">See also</span></span>

- [<span data-ttu-id="29867-121">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29867-121">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
