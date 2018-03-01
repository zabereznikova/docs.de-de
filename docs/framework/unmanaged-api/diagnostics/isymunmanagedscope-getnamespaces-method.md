---
title: ISymUnmanagedScope::GetNamespaces-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 25f6fc01d418693f62092d338cf93b1762bcfc8d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedscopegetnamespaces-method"></a><span data-ttu-id="7269d-102">ISymUnmanagedScope::GetNamespaces-Methode</span><span class="sxs-lookup"><span data-stu-id="7269d-102">ISymUnmanagedScope::GetNamespaces Method</span></span>
<span data-ttu-id="7269d-103">Ruft die Namespaces, die in diesem Bereich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7269d-103">Gets the namespaces that are being used within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7269d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7269d-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces),  
        length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7269d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7269d-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="7269d-106">[in] Die Größe des `namespaces`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="7269d-106">[in] The size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="7269d-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe des Puffers erforderlich, um die Namespaces zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="7269d-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="7269d-108">[out] Das Array, das die Namespaces empfängt.</span><span class="sxs-lookup"><span data-stu-id="7269d-108">[out] The array that receives the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7269d-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7269d-109">Return Value</span></span>  
 <span data-ttu-id="7269d-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="7269d-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7269d-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7269d-111">Requirements</span></span>  
 <span data-ttu-id="7269d-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7269d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7269d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7269d-113">See Also</span></span>  
 [<span data-ttu-id="7269d-114">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7269d-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
