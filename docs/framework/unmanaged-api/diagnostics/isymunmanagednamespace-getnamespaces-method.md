---
title: ISymUnmanagedNamespace::GetNamespaces-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedNamespace.GetNamespaces
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedNamespace::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedNamespace::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 0ea9d9af-8709-4a46-872b-f54d9e840088
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 69ee0f6385abf78a368d488d0190796516c4f3d7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="3452d-102">ISymUnmanagedNamespace::GetNamespaces-Methode</span><span class="sxs-lookup"><span data-stu-id="3452d-102">ISymUnmanagedNamespace::GetNamespaces Method</span></span>
<span data-ttu-id="3452d-103">Ruft die untergeordneten Elemente dieses Namespaces ab.</span><span class="sxs-lookup"><span data-stu-id="3452d-103">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3452d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3452d-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3452d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3452d-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="3452d-106">[in] Ein `ULONG32` , der angibt, dass der Größe des der `namespaces` Array.</span><span class="sxs-lookup"><span data-stu-id="3452d-106">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="3452d-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe Puffers in Zeichen, die erforderlich sind, um die Namespaces zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="3452d-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="3452d-108">[out] Ein Zeiger auf den Puffer, der die Namespaces enthält.</span><span class="sxs-lookup"><span data-stu-id="3452d-108">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3452d-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3452d-109">Return Value</span></span>  
 <span data-ttu-id="3452d-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="3452d-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3452d-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3452d-111">Requirements</span></span>  
 <span data-ttu-id="3452d-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3452d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3452d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3452d-113">See Also</span></span>  
 [<span data-ttu-id="3452d-114">ISymUnmanagedNamespace-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3452d-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
