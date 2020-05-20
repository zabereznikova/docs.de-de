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
ms.openlocfilehash: ab248c6a624fbed1a6783383566be093c449ff97
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609884"
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="20538-102">ISymUnmanagedWriter::OpenNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="20538-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>
<span data-ttu-id="20538-103">Öffnet einen neuen Namespace.</span><span class="sxs-lookup"><span data-stu-id="20538-103">Opens a new namespace.</span></span> <span data-ttu-id="20538-104">Diese Methode wird aufgerufen, bevor Methoden oder Variablen definiert werden, die einen Namespace belegen.</span><span class="sxs-lookup"><span data-stu-id="20538-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="20538-105">Namespaces können eingebettet werden.</span><span class="sxs-lookup"><span data-stu-id="20538-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20538-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="20538-106">Syntax</span></span>  
  
```cpp  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20538-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="20538-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="20538-108">in Ein Zeiger auf den Namen des neuen Namespace.</span><span class="sxs-lookup"><span data-stu-id="20538-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="20538-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="20538-109">Return Value</span></span>  
 <span data-ttu-id="20538-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="20538-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20538-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="20538-111">Requirements</span></span>  
 <span data-ttu-id="20538-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="20538-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20538-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20538-113">See also</span></span>

- [<span data-ttu-id="20538-114">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20538-114">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="20538-115">CloseNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="20538-115">CloseNamespace Method</span></span>](isymunmanagedwriter-closenamespace-method.md)
