---
title: ISymUnmanagedWriter::OpenScope-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenScope
helpviewer_keywords:
- OpenScope method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::OpenScope method [.NET Framework debugging]
ms.assetid: dbea0644-3873-4329-90b8-624163e87467
topic_type:
- apiref
ms.openlocfilehash: 2808606be24399c9a4fe03df4c53202d31cbbe91
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501715"
---
# <a name="isymunmanagedwriteropenscope-method"></a><span data-ttu-id="6e229-102">ISymUnmanagedWriter::OpenScope-Methode</span><span class="sxs-lookup"><span data-stu-id="6e229-102">ISymUnmanagedWriter::OpenScope Method</span></span>
<span data-ttu-id="6e229-103">Öffnet einen neuen lexikalischen Gültigkeitsbereich in der aktuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="6e229-103">Opens a new lexical scope in the current method.</span></span> <span data-ttu-id="6e229-104">Der Gültigkeitsbereich wird zum neuen aktuellen Bereich und wird auf einen Stapel von Bereichen übermittelt.</span><span class="sxs-lookup"><span data-stu-id="6e229-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="6e229-105">Bereiche müssen eine Hierarchie bilden.</span><span class="sxs-lookup"><span data-stu-id="6e229-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="6e229-106">Gleich geordnete Elemente dürfen sich nicht überlappen.</span><span class="sxs-lookup"><span data-stu-id="6e229-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e229-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="6e229-107">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope(  
    [in] ULONG32 startOffset,  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e229-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="6e229-108">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="6e229-109">in Der Offset der ersten Anweisung im lexikalischen Gültigkeitsbereich (in Bytes) vom Anfang der Methode.</span><span class="sxs-lookup"><span data-stu-id="6e229-109">[in] The offset of the first instruction in the lexical scope, in bytes, from the beginning of the method.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="6e229-110">vorgenommen Ein Zeiger auf einen `ULONG32` , der den Bereichs Bezeichner empfängt.</span><span class="sxs-lookup"><span data-stu-id="6e229-110">[out] A pointer to a `ULONG32` that receives the scope identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6e229-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6e229-111">Return Value</span></span>  
 <span data-ttu-id="6e229-112">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="6e229-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e229-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6e229-113">Remarks</span></span>  
 <span data-ttu-id="6e229-114">`ISymUnmanagedWriter::OpenScope`Gibt einen nicht transparenten Bereichs Bezeichner zurück, der mit [ISymUnmanagedWriter:: SetScopeRange](isymunmanagedwriter-setscoperange-method.md) verwendet werden kann, um den Start-und Endoffset eines Bereichs zu einem späteren Zeitpunkt zu definieren.</span><span class="sxs-lookup"><span data-stu-id="6e229-114">`ISymUnmanagedWriter::OpenScope` returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](isymunmanagedwriter-setscoperange-method.md) to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="6e229-115">In diesem Fall werden die an `ISymUnmanagedWriter::OpenScope` -und [ISymUnmanagedWriter:: CloseScope](isymunmanagedwriter-closescope-method.md) übergebenen Offsets ignoriert.</span><span class="sxs-lookup"><span data-stu-id="6e229-115">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="6e229-116">Bereichs Bezeichner sind nur in der aktuellen Methode gültig.</span><span class="sxs-lookup"><span data-stu-id="6e229-116">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e229-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6e229-117">Requirements</span></span>  
 <span data-ttu-id="6e229-118">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="6e229-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e229-119">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="6e229-119">See also</span></span>

- [<span data-ttu-id="6e229-120">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e229-120">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
