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
ms.openlocfilehash: 3ce2372be02bc0bae7097389d4933f1f28a4ed79
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427049"
---
# <a name="isymunmanagedscopegetchildren-method"></a><span data-ttu-id="08f2f-102">ISymUnmanagedScope::GetChildren-Methode</span><span class="sxs-lookup"><span data-stu-id="08f2f-102">ISymUnmanagedScope::GetChildren Method</span></span>
<span data-ttu-id="08f2f-103">Ruft die untergeordneten Elemente dieses Bereichs ab.</span><span class="sxs-lookup"><span data-stu-id="08f2f-103">Gets the children of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08f2f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="08f2f-104">Syntax</span></span>  
  
```  
HRESULT GetChildren(  
    [in]  ULONG32  cChildren,  
    [out] ULONG32  *pcChildren,  
    [out, size_is(cChildren),  
        length_is(*pcChildren)] ISymUnmanagedScope* children[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="08f2f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="08f2f-105">Parameters</span></span>  
 `cChildren`  
 <span data-ttu-id="08f2f-106">[in] Ein `ULONG32` , der angibt, dass der Größe des der `children` Array.</span><span class="sxs-lookup"><span data-stu-id="08f2f-106">[in] A `ULONG32` that indicates the size of the `children` array.</span></span>  
  
 `pcChildren`  
 <span data-ttu-id="08f2f-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe des Puffers erforderlich, um die untergeordneten Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="08f2f-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the children.</span></span>  
  
 `children`  
 <span data-ttu-id="08f2f-108">[out] Das zurückgegebene Array untergeordneter Elemente.</span><span class="sxs-lookup"><span data-stu-id="08f2f-108">[out] The returned array of children.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08f2f-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="08f2f-109">Return Value</span></span>  
 <span data-ttu-id="08f2f-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="08f2f-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08f2f-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="08f2f-111">Requirements</span></span>  
 <span data-ttu-id="08f2f-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="08f2f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08f2f-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08f2f-113">See Also</span></span>  
 [<span data-ttu-id="08f2f-114">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08f2f-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 [<span data-ttu-id="08f2f-115">GetParent-Methode</span><span class="sxs-lookup"><span data-stu-id="08f2f-115">GetParent Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)
