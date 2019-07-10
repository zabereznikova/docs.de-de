---
title: ISymUnmanagedWriter::UsingNamespace-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.UsingNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::UsingNamespace
helpviewer_keywords:
- UsingNamespace method [.NET Framework debugging]
- ISymUnmanagedWriter::UsingNamespace method [.NET Framework debugging]
ms.assetid: 8d746e0a-d158-4983-88da-db0a0856bc0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0076b70c85c21f0c4b1fb140b15000f99dbff742
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755133"
---
# <a name="isymunmanagedwriterusingnamespace-method"></a><span data-ttu-id="29632-102">ISymUnmanagedWriter::UsingNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="29632-102">ISymUnmanagedWriter::UsingNamespace Method</span></span>
<span data-ttu-id="29632-103">Gibt an, dass es sich bei der angegebenen Namen für den vollqualifizierten Namespace im geöffneten lexikalischen Gültigkeitsbereich verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="29632-103">Specifies that the given fully qualified namespace name is being used within the currently open lexical scope.</span></span> <span data-ttu-id="29632-104">Der Namespace wird in allen Bereichen verwendet, die von der aktuell geöffneten Bereich erben.</span><span class="sxs-lookup"><span data-stu-id="29632-104">The namespace will be used within all scopes that inherit from the currently open scope.</span></span> <span data-ttu-id="29632-105">Schließen den aktuellen Bereich wird die Verwendung des Namespace auch beendet werden.</span><span class="sxs-lookup"><span data-stu-id="29632-105">Closing the current scope will also stop the use of the namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29632-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="29632-106">Syntax</span></span>  
  
```cpp  
HRESULT UsingNamespace(  
    [in] const WCHAR *fullName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29632-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="29632-107">Parameters</span></span>  
 `fullName`  
 <span data-ttu-id="29632-108">[in] Ein Zeiger auf den vollqualifizierten Namen des Namespaces.</span><span class="sxs-lookup"><span data-stu-id="29632-108">[in] A pointer to the fully qualified name of the namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="29632-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="29632-109">Return Value</span></span>  
 <span data-ttu-id="29632-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="29632-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29632-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="29632-111">Requirements</span></span>  
 <span data-ttu-id="29632-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="29632-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29632-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29632-113">See also</span></span>

- [<span data-ttu-id="29632-114">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29632-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
