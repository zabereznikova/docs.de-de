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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1585acce8bba0dff327c961f5e32ef6b46794401
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986023"
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="8bdfd-102">ISymUnmanagedWriter::OpenNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="8bdfd-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>
<span data-ttu-id="8bdfd-103">Öffnet einen neuen Namespace.</span><span class="sxs-lookup"><span data-stu-id="8bdfd-103">Opens a new namespace.</span></span> <span data-ttu-id="8bdfd-104">Rufen Sie diese Methode vor dem Definieren von Methoden und Variablen, die einen Namespace zu belegen.</span><span class="sxs-lookup"><span data-stu-id="8bdfd-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="8bdfd-105">Namespaces können geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="8bdfd-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bdfd-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="8bdfd-106">Syntax</span></span>  
  
```  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bdfd-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="8bdfd-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="8bdfd-108">[in] Ein Zeiger auf den Namen des neuen Namespaces.</span><span class="sxs-lookup"><span data-stu-id="8bdfd-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8bdfd-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8bdfd-109">Return Value</span></span>  
 <span data-ttu-id="8bdfd-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="8bdfd-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bdfd-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8bdfd-111">Requirements</span></span>  
 <span data-ttu-id="8bdfd-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8bdfd-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bdfd-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8bdfd-113">See also</span></span>

- [<span data-ttu-id="8bdfd-114">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8bdfd-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="8bdfd-115">CloseNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="8bdfd-115">CloseNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)
