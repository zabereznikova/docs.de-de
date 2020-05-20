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
ms.openlocfilehash: 44f9284f0a89f0941940cf379c48b2b138149122
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614941"
---
# <a name="isymunmanagedreadergetnamespaces-method"></a><span data-ttu-id="78689-102">ISymUnmanagedReader::GetNamespaces-Methode</span><span class="sxs-lookup"><span data-stu-id="78689-102">ISymUnmanagedReader::GetNamespaces Method</span></span>
<span data-ttu-id="78689-103">Ruft die Namespaces ab, die im globalen Gültigkeitsbereich innerhalb dieses Symbol Speicher definiert sind.</span><span class="sxs-lookup"><span data-stu-id="78689-103">Gets the namespaces defined at global scope within this symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78689-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="78689-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces (  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is (cNameSpaces),  
        length_is (*pcNameSpaces)]  
        ISymUnmanagedNamespace*  namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78689-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="78689-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="78689-106">in Die Größe des Namespaces-Arrays.</span><span class="sxs-lookup"><span data-stu-id="78689-106">[in] The size of the namespaces array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="78689-107">vorgenommen Ein Zeiger auf eine Variable, die die Länge der Namespace Liste empfängt.</span><span class="sxs-lookup"><span data-stu-id="78689-107">[out] A pointer to a variable that receives the length of the namespace list.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="78689-108">vorgenommen Ein Zeiger auf eine Variable, die die Namespace Liste empfängt.</span><span class="sxs-lookup"><span data-stu-id="78689-108">[out] A pointer to a variable that receives the namespace list.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="78689-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="78689-109">Return Value</span></span>  
 <span data-ttu-id="78689-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="78689-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78689-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="78689-111">Requirements</span></span>  
 <span data-ttu-id="78689-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="78689-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78689-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78689-113">See also</span></span>

- [<span data-ttu-id="78689-114">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="78689-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
