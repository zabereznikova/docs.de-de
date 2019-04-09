---
title: ISymUnmanagedScope::GetNamespaces-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetNamespaces
helpviewer_keywords:
- GetNamespaces method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetNamespaces method [.NET Framework debugging]
ms.assetid: c44b0440-04bd-460a-84fb-41afecf44503
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3dc3c842bbb4b86b82d03848751673400bed193b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213037"
---
# <a name="isymunmanagedscopegetnamespaces-method"></a><span data-ttu-id="06246-102">ISymUnmanagedScope::GetNamespaces-Methode</span><span class="sxs-lookup"><span data-stu-id="06246-102">ISymUnmanagedScope::GetNamespaces Method</span></span>
<span data-ttu-id="06246-103">Ruft die Namespaces, die innerhalb dieses Bereichs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="06246-103">Gets the namespaces that are being used within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06246-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="06246-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces),  
        length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06246-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="06246-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="06246-106">[in] Die Größe des `namespaces`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="06246-106">[in] The size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="06246-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe des Puffers erforderlich, um die Namespaces enthalten.</span><span class="sxs-lookup"><span data-stu-id="06246-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="06246-108">[out] Das Array, das die Namespaces empfängt.</span><span class="sxs-lookup"><span data-stu-id="06246-108">[out] The array that receives the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06246-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="06246-109">Return Value</span></span>  
 <span data-ttu-id="06246-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="06246-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06246-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="06246-111">Requirements</span></span>  
 <span data-ttu-id="06246-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="06246-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06246-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06246-113">See also</span></span>

- [<span data-ttu-id="06246-114">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="06246-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
