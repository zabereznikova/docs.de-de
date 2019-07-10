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
ms.openlocfilehash: 2e11886917964134a2530ae8484dba3cde5e7b61
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759373"
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="0452c-102">ISymUnmanagedNamespace::GetNamespaces-Methode</span><span class="sxs-lookup"><span data-stu-id="0452c-102">ISymUnmanagedNamespace::GetNamespaces Method</span></span>
<span data-ttu-id="0452c-103">Ruft die untergeordneten Elemente dieses Namespaces ab.</span><span class="sxs-lookup"><span data-stu-id="0452c-103">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0452c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0452c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0452c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0452c-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="0452c-106">[in] Ein `ULONG32` , der angibt, dass der Größe des der `namespaces` Array.</span><span class="sxs-lookup"><span data-stu-id="0452c-106">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="0452c-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe des für die Namespaces enthalten die erforderlichen Puffers in Zeichen.</span><span class="sxs-lookup"><span data-stu-id="0452c-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="0452c-108">[out] Ein Zeiger auf den Puffer, der die Namespaces enthält.</span><span class="sxs-lookup"><span data-stu-id="0452c-108">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0452c-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0452c-109">Return Value</span></span>  
 <span data-ttu-id="0452c-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="0452c-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0452c-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0452c-111">Requirements</span></span>  
 <span data-ttu-id="0452c-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0452c-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0452c-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0452c-113">See also</span></span>

- [<span data-ttu-id="0452c-114">ISymUnmanagedNamespace-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0452c-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
