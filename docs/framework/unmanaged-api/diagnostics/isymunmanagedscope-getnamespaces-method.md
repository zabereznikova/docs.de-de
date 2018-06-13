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
ms.openlocfilehash: c786cd43a25aa0c69c19e57452a3b190c7bfb167
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426840"
---
# <a name="isymunmanagedscopegetnamespaces-method"></a><span data-ttu-id="28b10-102">ISymUnmanagedScope::GetNamespaces-Methode</span><span class="sxs-lookup"><span data-stu-id="28b10-102">ISymUnmanagedScope::GetNamespaces Method</span></span>
<span data-ttu-id="28b10-103">Ruft die Namespaces, die in diesem Bereich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="28b10-103">Gets the namespaces that are being used within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28b10-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="28b10-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces),  
        length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="28b10-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="28b10-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="28b10-106">[in] Die Größe des `namespaces`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="28b10-106">[in] The size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="28b10-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe des Puffers erforderlich, um die Namespaces zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="28b10-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="28b10-108">[out] Das Array, das die Namespaces empfängt.</span><span class="sxs-lookup"><span data-stu-id="28b10-108">[out] The array that receives the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="28b10-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="28b10-109">Return Value</span></span>  
 <span data-ttu-id="28b10-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="28b10-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28b10-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="28b10-111">Requirements</span></span>  
 <span data-ttu-id="28b10-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="28b10-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28b10-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28b10-113">See Also</span></span>  
 [<span data-ttu-id="28b10-114">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="28b10-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
