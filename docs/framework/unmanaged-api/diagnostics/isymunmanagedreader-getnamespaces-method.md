---
title: ISymUnmanagedReader::GetNamespaces-Methode
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
- ISymUnmanagedReader.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedReader::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 3feb4796-2fab-45ce-beca-6f5bc530b971
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9db8875acfd4df2cd889cc2e6d606aba252fa33f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetnamespaces-method"></a><span data-ttu-id="ec1fb-102">ISymUnmanagedReader::GetNamespaces-Methode</span><span class="sxs-lookup"><span data-stu-id="ec1fb-102">ISymUnmanagedReader::GetNamespaces Method</span></span>
<span data-ttu-id="ec1fb-103">Ruft die im globalen Gültigkeitsbereich in diesem Symbolspeicher definierten Namespaces ab.</span><span class="sxs-lookup"><span data-stu-id="ec1fb-103">Gets the namespaces defined at global scope within this symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec1fb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec1fb-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces (  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is (cNameSpaces),  
        length_is (*pcNameSpaces)]  
        ISymUnmanagedNamespace*  namespaces[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ec1fb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ec1fb-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="ec1fb-106">[in] Die Größe des Namespacearrays.</span><span class="sxs-lookup"><span data-stu-id="ec1fb-106">[in] The size of the namespaces array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="ec1fb-107">[out] Ein Zeiger auf eine Variable, die die Länge der Namespaceliste empfängt.</span><span class="sxs-lookup"><span data-stu-id="ec1fb-107">[out] A pointer to a variable that receives the length of the namespace list.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="ec1fb-108">[out] Ein Zeiger auf eine Variable, die die Namespaceliste empfängt.</span><span class="sxs-lookup"><span data-stu-id="ec1fb-108">[out] A pointer to a variable that receives the namespace list.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec1fb-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ec1fb-109">Return Value</span></span>  
 <span data-ttu-id="ec1fb-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="ec1fb-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec1fb-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ec1fb-111">Requirements</span></span>  
 <span data-ttu-id="ec1fb-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ec1fb-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec1fb-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec1fb-113">See Also</span></span>  
 [<span data-ttu-id="ec1fb-114">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ec1fb-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
