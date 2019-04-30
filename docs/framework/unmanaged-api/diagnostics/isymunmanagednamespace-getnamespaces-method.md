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
ms.openlocfilehash: 3d7ac84971f7d0e97f7ccd26710151d1aeefe729
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939502"
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="38c83-102">ISymUnmanagedNamespace::GetNamespaces-Methode</span><span class="sxs-lookup"><span data-stu-id="38c83-102">ISymUnmanagedNamespace::GetNamespaces Method</span></span>
<span data-ttu-id="38c83-103">Ruft die untergeordneten Elemente dieses Namespaces ab.</span><span class="sxs-lookup"><span data-stu-id="38c83-103">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38c83-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="38c83-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38c83-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="38c83-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="38c83-106">[in] Ein `ULONG32` , der angibt, dass der Größe des der `namespaces` Array.</span><span class="sxs-lookup"><span data-stu-id="38c83-106">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="38c83-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe des für die Namespaces enthalten die erforderlichen Puffers in Zeichen.</span><span class="sxs-lookup"><span data-stu-id="38c83-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="38c83-108">[out] Ein Zeiger auf den Puffer, der die Namespaces enthält.</span><span class="sxs-lookup"><span data-stu-id="38c83-108">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="38c83-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="38c83-109">Return Value</span></span>  
 <span data-ttu-id="38c83-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="38c83-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38c83-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="38c83-111">Requirements</span></span>  
 <span data-ttu-id="38c83-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="38c83-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38c83-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38c83-113">See also</span></span>

- [<span data-ttu-id="38c83-114">ISymUnmanagedNamespace-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="38c83-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
