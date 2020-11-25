---
title: ISymUnmanagedWriter::OpenNamespace-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::OpenNamespace method [.NET Framework debugging]
- OpenNamespace method [.NET Framework debugging]
ms.assetid: 426f4e4f-e60d-4ad1-b546-a10e3c55c283
topic_type:
- apiref
ms.openlocfilehash: 2f64f9f4bde3119f9f089becec5a36d69ed43596
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730060"
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="13d4b-102">ISymUnmanagedWriter::OpenNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="13d4b-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>

<span data-ttu-id="13d4b-103">Öffnet einen neuen Namespace.</span><span class="sxs-lookup"><span data-stu-id="13d4b-103">Opens a new namespace.</span></span> <span data-ttu-id="13d4b-104">Diese Methode wird aufgerufen, bevor Methoden oder Variablen definiert werden, die einen Namespace belegen.</span><span class="sxs-lookup"><span data-stu-id="13d4b-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="13d4b-105">Namespaces können eingebettet werden.</span><span class="sxs-lookup"><span data-stu-id="13d4b-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13d4b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="13d4b-106">Syntax</span></span>  
  
```cpp  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13d4b-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="13d4b-107">Parameters</span></span>  

 `name`  
 <span data-ttu-id="13d4b-108">in Ein Zeiger auf den Namen des neuen Namespace.</span><span class="sxs-lookup"><span data-stu-id="13d4b-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="13d4b-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="13d4b-109">Return Value</span></span>  

 <span data-ttu-id="13d4b-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="13d4b-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13d4b-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="13d4b-111">Requirements</span></span>  

 <span data-ttu-id="13d4b-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="13d4b-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13d4b-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="13d4b-113">See also</span></span>

- [<span data-ttu-id="13d4b-114">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="13d4b-114">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="13d4b-115">CloseNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="13d4b-115">CloseNamespace Method</span></span>](isymunmanagedwriter-closenamespace-method.md)
