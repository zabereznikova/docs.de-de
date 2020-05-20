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
ms.openlocfilehash: 48c50ac6be6d525676d85578e5a55a27104c180a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615097"
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="fb7ef-102">ISymUnmanagedNamespace::GetNamespaces-Methode</span><span class="sxs-lookup"><span data-stu-id="fb7ef-102">ISymUnmanagedNamespace::GetNamespaces Method</span></span>
<span data-ttu-id="fb7ef-103">Ruft die untergeordneten Elemente dieses Namespace ab.</span><span class="sxs-lookup"><span data-stu-id="fb7ef-103">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb7ef-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb7ef-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb7ef-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fb7ef-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="fb7ef-106">in Ein-Wert `ULONG32` , der die Größe des `namespaces` Arrays angibt.</span><span class="sxs-lookup"><span data-stu-id="fb7ef-106">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="fb7ef-107">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers, der die Namespaces enthalten muss, in Zeichen empfängt.</span><span class="sxs-lookup"><span data-stu-id="fb7ef-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="fb7ef-108">vorgenommen Ein Zeiger auf den Puffer, der die Namespaces enthält.</span><span class="sxs-lookup"><span data-stu-id="fb7ef-108">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fb7ef-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fb7ef-109">Return Value</span></span>  
 <span data-ttu-id="fb7ef-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="fb7ef-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb7ef-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fb7ef-111">Requirements</span></span>  
 <span data-ttu-id="fb7ef-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="fb7ef-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb7ef-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb7ef-113">See also</span></span>

- [<span data-ttu-id="fb7ef-114">ISymUnmanagedNamespace-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fb7ef-114">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)
