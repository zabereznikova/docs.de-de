---
title: ISymUnmanagedScope::GetChildren-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetChildren
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetChildren
helpviewer_keywords:
- ISymUnmanagedScope::GetChildren method [.NET Framework debugging]
- GetChildren method [.NET Framework debugging]
ms.assetid: 0bed524e-cc48-4bf0-b9fa-25d665e63ddb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3cad217ddf2d5354ad019f26fd10fb9ccd004d61
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133899"
---
# <a name="isymunmanagedscopegetchildren-method"></a><span data-ttu-id="ba8c8-102">ISymUnmanagedScope::GetChildren-Methode</span><span class="sxs-lookup"><span data-stu-id="ba8c8-102">ISymUnmanagedScope::GetChildren Method</span></span>
<span data-ttu-id="ba8c8-103">Ruft die untergeordneten Elemente dieses Bereichs ab.</span><span class="sxs-lookup"><span data-stu-id="ba8c8-103">Gets the children of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba8c8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ba8c8-104">Syntax</span></span>  
  
```  
HRESULT GetChildren(  
    [in]  ULONG32  cChildren,  
    [out] ULONG32  *pcChildren,  
    [out, size_is(cChildren),  
        length_is(*pcChildren)] ISymUnmanagedScope* children[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba8c8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ba8c8-105">Parameters</span></span>  
 `cChildren`  
 <span data-ttu-id="ba8c8-106">[in] Ein `ULONG32` , der angibt, dass der Größe des der `children` Array.</span><span class="sxs-lookup"><span data-stu-id="ba8c8-106">[in] A `ULONG32` that indicates the size of the `children` array.</span></span>  
  
 `pcChildren`  
 <span data-ttu-id="ba8c8-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe des Puffers erforderlich, um die untergeordneten Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="ba8c8-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the children.</span></span>  
  
 `children`  
 <span data-ttu-id="ba8c8-108">[out] Das zurückgegebene Array der untergeordneten Elemente.</span><span class="sxs-lookup"><span data-stu-id="ba8c8-108">[out] The returned array of children.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba8c8-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ba8c8-109">Return Value</span></span>  
 <span data-ttu-id="ba8c8-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="ba8c8-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba8c8-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ba8c8-111">Requirements</span></span>  
 <span data-ttu-id="ba8c8-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ba8c8-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba8c8-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba8c8-113">See also</span></span>

- [<span data-ttu-id="ba8c8-114">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ba8c8-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="ba8c8-115">GetParent-Methode</span><span class="sxs-lookup"><span data-stu-id="ba8c8-115">GetParent Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)
