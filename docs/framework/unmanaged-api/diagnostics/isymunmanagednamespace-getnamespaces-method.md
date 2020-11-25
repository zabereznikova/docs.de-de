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
ms.openlocfilehash: 8eef973c4c054b704b7c3f798e5dc1aa455dda96
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707774"
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="4bb23-102">ISymUnmanagedNamespace::GetNamespaces-Methode</span><span class="sxs-lookup"><span data-stu-id="4bb23-102">ISymUnmanagedNamespace::GetNamespaces Method</span></span>

<span data-ttu-id="4bb23-103">Ruft die untergeordneten Elemente dieses Namespace ab.</span><span class="sxs-lookup"><span data-stu-id="4bb23-103">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bb23-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4bb23-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4bb23-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4bb23-105">Parameters</span></span>  

 `cNameSpaces`  
 <span data-ttu-id="4bb23-106">in Ein-Wert `ULONG32` , der die Größe des `namespaces` Arrays angibt.</span><span class="sxs-lookup"><span data-stu-id="4bb23-106">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="4bb23-107">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers, der die Namespaces enthalten muss, in Zeichen empfängt.</span><span class="sxs-lookup"><span data-stu-id="4bb23-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="4bb23-108">vorgenommen Ein Zeiger auf den Puffer, der die Namespaces enthält.</span><span class="sxs-lookup"><span data-stu-id="4bb23-108">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4bb23-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4bb23-109">Return Value</span></span>  

 <span data-ttu-id="4bb23-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="4bb23-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bb23-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4bb23-111">Requirements</span></span>  

 <span data-ttu-id="4bb23-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="4bb23-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bb23-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4bb23-113">See also</span></span>

- [<span data-ttu-id="4bb23-114">ISymUnmanagedNamespace-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4bb23-114">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)
