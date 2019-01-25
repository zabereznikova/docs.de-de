---
title: ISymUnmanagedReader::GetNamespaces-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5227de340bec85620f8c8d45538ad9a9d7f688fb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54630956"
---
# <a name="isymunmanagedreadergetnamespaces-method"></a><span data-ttu-id="10c92-102">ISymUnmanagedReader::GetNamespaces-Methode</span><span class="sxs-lookup"><span data-stu-id="10c92-102">ISymUnmanagedReader::GetNamespaces Method</span></span>
<span data-ttu-id="10c92-103">Ruft die Namespaces, die auf diesem Symbolspeicher mit globalem Gültigkeitsbereich definiert.</span><span class="sxs-lookup"><span data-stu-id="10c92-103">Gets the namespaces defined at global scope within this symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10c92-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="10c92-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces (  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is (cNameSpaces),  
        length_is (*pcNameSpaces)]  
        ISymUnmanagedNamespace*  namespaces[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="10c92-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="10c92-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="10c92-106">[in] Die Größe des Namespacearrays.</span><span class="sxs-lookup"><span data-stu-id="10c92-106">[in] The size of the namespaces array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="10c92-107">[out] Ein Zeiger auf eine Variable, die die Länge der Liste der Namespaces empfängt.</span><span class="sxs-lookup"><span data-stu-id="10c92-107">[out] A pointer to a variable that receives the length of the namespace list.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="10c92-108">[out] Ein Zeiger auf eine Variable, die der Liste der Namespaces empfängt.</span><span class="sxs-lookup"><span data-stu-id="10c92-108">[out] A pointer to a variable that receives the namespace list.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10c92-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="10c92-109">Return Value</span></span>  
 <span data-ttu-id="10c92-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="10c92-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10c92-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="10c92-111">Requirements</span></span>  
 <span data-ttu-id="10c92-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="10c92-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10c92-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10c92-113">See also</span></span>
- [<span data-ttu-id="10c92-114">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="10c92-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
