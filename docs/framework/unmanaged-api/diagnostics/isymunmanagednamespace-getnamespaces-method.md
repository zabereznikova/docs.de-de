---
title: ISymUnmanagedNamespace::GetNamespaces-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedNamespace::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 0ea9d9af-8709-4a46-872b-f54d9e840088
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a874c1493e1f8aaa18354de26905fabd3a793129
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674543"
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="acf51-102">ISymUnmanagedNamespace::GetNamespaces-Methode</span><span class="sxs-lookup"><span data-stu-id="acf51-102">ISymUnmanagedNamespace::GetNamespaces Method</span></span>
<span data-ttu-id="acf51-103">Ruft die untergeordneten Elemente dieses Namespaces ab.</span><span class="sxs-lookup"><span data-stu-id="acf51-103">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acf51-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="acf51-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="acf51-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="acf51-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="acf51-106">[in] Ein `ULONG32` , der angibt, dass der Größe des der `namespaces` Array.</span><span class="sxs-lookup"><span data-stu-id="acf51-106">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="acf51-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe des für die Namespaces enthalten die erforderlichen Puffers in Zeichen.</span><span class="sxs-lookup"><span data-stu-id="acf51-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="acf51-108">[out] Ein Zeiger auf den Puffer, der die Namespaces enthält.</span><span class="sxs-lookup"><span data-stu-id="acf51-108">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="acf51-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="acf51-109">Return Value</span></span>  
 <span data-ttu-id="acf51-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="acf51-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acf51-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="acf51-111">Requirements</span></span>  
 <span data-ttu-id="acf51-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="acf51-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acf51-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="acf51-113">See also</span></span>
- [<span data-ttu-id="acf51-114">ISymUnmanagedNamespace-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="acf51-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
