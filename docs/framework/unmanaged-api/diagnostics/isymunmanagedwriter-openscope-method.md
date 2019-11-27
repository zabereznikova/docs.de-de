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
ms.openlocfilehash: 915b05d0d2ac611678fdcc94dd42bbb1962e6ceb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427893"
---
# <a name="isymunmanagedwriteropenscope-method"></a><span data-ttu-id="e1538-102">ISymUnmanagedWriter::OpenScope-Methode</span><span class="sxs-lookup"><span data-stu-id="e1538-102">ISymUnmanagedWriter::OpenScope Method</span></span>
<span data-ttu-id="e1538-103">Öffnet einen neuen lexikalischen Gültigkeitsbereich in der aktuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="e1538-103">Opens a new lexical scope in the current method.</span></span> <span data-ttu-id="e1538-104">Der Gültigkeitsbereich wird zum neuen aktuellen Bereich und wird auf einen Stapel von Bereichen übermittelt.</span><span class="sxs-lookup"><span data-stu-id="e1538-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="e1538-105">Bereiche müssen eine Hierarchie bilden.</span><span class="sxs-lookup"><span data-stu-id="e1538-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="e1538-106">Gleich geordnete Elemente dürfen sich nicht überlappen.</span><span class="sxs-lookup"><span data-stu-id="e1538-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1538-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="e1538-107">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope(  
    [in] ULONG32 startOffset,  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1538-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="e1538-108">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="e1538-109">in Der Offset der ersten Anweisung im lexikalischen Gültigkeitsbereich (in Bytes) vom Anfang der Methode.</span><span class="sxs-lookup"><span data-stu-id="e1538-109">[in] The offset of the first instruction in the lexical scope, in bytes, from the beginning of the method.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="e1538-110">vorgenommen Ein Zeiger auf einen `ULONG32`, der den Bereichs Bezeichner empfängt.</span><span class="sxs-lookup"><span data-stu-id="e1538-110">[out] A pointer to a `ULONG32` that receives the scope identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e1538-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e1538-111">Return Value</span></span>  
 <span data-ttu-id="e1538-112">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="e1538-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1538-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e1538-113">Remarks</span></span>  
 <span data-ttu-id="e1538-114">`ISymUnmanagedWriter::OpenScope` gibt einen nicht transparenten Bereichs Bezeichner zurück, der mit [ISymUnmanagedWriter:: SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) verwendet werden kann, um den Start-und Endoffset eines Bereichs zu einem späteren Zeitpunkt zu definieren.</span><span class="sxs-lookup"><span data-stu-id="e1538-114">`ISymUnmanagedWriter::OpenScope` returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="e1538-115">In diesem Fall werden die an `ISymUnmanagedWriter::OpenScope` und [ISymUnmanagedWriter:: CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) übergebenen Offsets ignoriert.</span><span class="sxs-lookup"><span data-stu-id="e1538-115">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="e1538-116">Bereichs Bezeichner sind nur in der aktuellen Methode gültig.</span><span class="sxs-lookup"><span data-stu-id="e1538-116">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1538-117">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="e1538-117">Requirements</span></span>  
 <span data-ttu-id="e1538-118">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="e1538-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1538-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1538-119">See also</span></span>

- [<span data-ttu-id="e1538-120">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e1538-120">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
