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
ms.openlocfilehash: e4348cc59924b65b6c6bb53a9c2a98f1a1161b50
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614733"
---
# <a name="isymunmanagedwriterusingnamespace-method"></a><span data-ttu-id="c8a97-102">ISymUnmanagedWriter::UsingNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="c8a97-102">ISymUnmanagedWriter::UsingNamespace Method</span></span>
<span data-ttu-id="c8a97-103">Gibt an, dass der angegebene voll qualifizierte Namespace Name innerhalb des derzeit geöffneten lexikalischen Gültigkeits Bereichs verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c8a97-103">Specifies that the given fully qualified namespace name is being used within the currently open lexical scope.</span></span> <span data-ttu-id="c8a97-104">Der-Namespace wird innerhalb aller Bereiche verwendet, die vom derzeit geöffneten Bereich erben.</span><span class="sxs-lookup"><span data-stu-id="c8a97-104">The namespace will be used within all scopes that inherit from the currently open scope.</span></span> <span data-ttu-id="c8a97-105">Wenn Sie den aktuellen Bereich schließen, wird auch die Verwendung des-Namespaces beendet.</span><span class="sxs-lookup"><span data-stu-id="c8a97-105">Closing the current scope will also stop the use of the namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8a97-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8a97-106">Syntax</span></span>  
  
```cpp  
HRESULT UsingNamespace(  
    [in] const WCHAR *fullName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8a97-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="c8a97-107">Parameters</span></span>  
 `fullName`  
 <span data-ttu-id="c8a97-108">in Ein Zeiger auf den voll qualifizierten Namen des Namespace.</span><span class="sxs-lookup"><span data-stu-id="c8a97-108">[in] A pointer to the fully qualified name of the namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8a97-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c8a97-109">Return Value</span></span>  
 <span data-ttu-id="c8a97-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="c8a97-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8a97-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c8a97-111">Requirements</span></span>  
 <span data-ttu-id="c8a97-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="c8a97-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8a97-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8a97-113">See also</span></span>

- [<span data-ttu-id="c8a97-114">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c8a97-114">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
