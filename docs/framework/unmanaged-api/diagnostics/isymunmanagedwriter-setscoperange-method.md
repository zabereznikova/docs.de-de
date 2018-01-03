---
title: ISymUnmanagedWriter::SetScopeRange-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.SetScopeRange
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::SetScopeRange
helpviewer_keywords:
- SetScopeRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetScopeRange method [.NET Framework debugging]
ms.assetid: d4d98676-444b-46ca-bfe6-0d827385cd22
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9afb0038adc4273033fb9f1db1ebc57f43eae779
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwritersetscoperange-method"></a><span data-ttu-id="95b6c-102">ISymUnmanagedWriter::SetScopeRange-Methode</span><span class="sxs-lookup"><span data-stu-id="95b6c-102">ISymUnmanagedWriter::SetScopeRange Method</span></span>
<span data-ttu-id="95b6c-103">Definiert den Offsetbereich für den angegebenen lexikalischen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="95b6c-103">Defines the offset range for the specified lexical scope.</span></span> <span data-ttu-id="95b6c-104">Der Bereich wird der neue aktuelle Bereich und wird auf einen Stapel von Bereichen abgelegt.</span><span class="sxs-lookup"><span data-stu-id="95b6c-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="95b6c-105">Bereiche müssen eine Hierarchie zu bilden.</span><span class="sxs-lookup"><span data-stu-id="95b6c-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="95b6c-106">Gleichgeordnete Elemente dürfen sich nicht überlappen.</span><span class="sxs-lookup"><span data-stu-id="95b6c-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95b6c-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="95b6c-107">Syntax</span></span>  
  
```  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="95b6c-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="95b6c-108">Parameters</span></span>  
 `scopeId`  
 <span data-ttu-id="95b6c-109">[in] Der Bereichsbezeichner für den Bereich.</span><span class="sxs-lookup"><span data-stu-id="95b6c-109">[in] The scope identifier for the scope.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="95b6c-110">[in] Der Offset in Bytes, der ersten Anweisung im lexikalischen Gültigkeitsbereich ab dem Anfang der Methode.</span><span class="sxs-lookup"><span data-stu-id="95b6c-110">[in] The offset, in bytes, of the first instruction in the lexical scope from the beginning of the method.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="95b6c-111">[in] Der Offset in Bytes, der die letzte Anweisung im lexikalischen Gültigkeitsbereich ab dem Anfang der Methode.</span><span class="sxs-lookup"><span data-stu-id="95b6c-111">[in] The offset, in bytes, of the last instruction in the lexical scope from the beginning of the method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95b6c-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="95b6c-112">Return Value</span></span>  
 <span data-ttu-id="95b6c-113">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="95b6c-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95b6c-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="95b6c-114">Remarks</span></span>  
 <span data-ttu-id="95b6c-115">[ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) gibt einen nicht transparenter Bezeichner, die mit verwendet werden kann `ISymUnmanagedWriter::SetScopeRange` zum Definieren eines Bereichs den Anfangs- und Endoffset zu einem späteren Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="95b6c-115">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with `ISymUnmanagedWriter::SetScopeRange` to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="95b6c-116">In diesem Fall das an die Offsets `ISymUnmanagedWriter::OpenScope` und [ISymUnmanagedWriter:: CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="95b6c-116">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="95b6c-117">Bereichsbezeichnern sind nur in der aktuellen Methode gültig.</span><span class="sxs-lookup"><span data-stu-id="95b6c-117">Scope identifiers are only valid in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95b6c-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="95b6c-118">Requirements</span></span>  
 <span data-ttu-id="95b6c-119">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="95b6c-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95b6c-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="95b6c-120">See Also</span></span>  
 [<span data-ttu-id="95b6c-121">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="95b6c-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
