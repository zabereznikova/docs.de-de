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
# <a name="isymunmanagedwriteropenscope-method"></a><span data-ttu-id="31940-102">ISymUnmanagedWriter::OpenScope-Methode</span><span class="sxs-lookup"><span data-stu-id="31940-102">ISymUnmanagedWriter::OpenScope Method</span></span>
<span data-ttu-id="31940-103">Öffnet einen neuen lexikalischen Gültigkeitsbereich in der aktuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="31940-103">Opens a new lexical scope in the current method.</span></span> <span data-ttu-id="31940-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span><span class="sxs-lookup"><span data-stu-id="31940-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="31940-105">Scopes must form a hierarchy.</span><span class="sxs-lookup"><span data-stu-id="31940-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="31940-106">Siblings are not allowed to overlap.</span><span class="sxs-lookup"><span data-stu-id="31940-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31940-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="31940-107">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope(  
    [in] ULONG32 startOffset,  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31940-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="31940-108">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="31940-109">[in] The offset of the first instruction in the lexical scope, in bytes, from the beginning of the method.</span><span class="sxs-lookup"><span data-stu-id="31940-109">[in] The offset of the first instruction in the lexical scope, in bytes, from the beginning of the method.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="31940-110">[out] A pointer to a `ULONG32` that receives the scope identifier.</span><span class="sxs-lookup"><span data-stu-id="31940-110">[out] A pointer to a `ULONG32` that receives the scope identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="31940-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="31940-111">Return Value</span></span>  
 <span data-ttu-id="31940-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="31940-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31940-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="31940-113">Remarks</span></span>  
 <span data-ttu-id="31940-114">`ISymUnmanagedWriter::OpenScope` returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to define a scope's starting and ending offset at a later time.</span><span class="sxs-lookup"><span data-stu-id="31940-114">`ISymUnmanagedWriter::OpenScope` returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="31940-115">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span><span class="sxs-lookup"><span data-stu-id="31940-115">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="31940-116">Scope identifiers are valid only in the current method.</span><span class="sxs-lookup"><span data-stu-id="31940-116">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31940-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="31940-117">Requirements</span></span>  
 <span data-ttu-id="31940-118">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="31940-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31940-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31940-119">See also</span></span>

- [<span data-ttu-id="31940-120">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31940-120">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
