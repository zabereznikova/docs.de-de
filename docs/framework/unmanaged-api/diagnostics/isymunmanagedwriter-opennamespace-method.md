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
ms.openlocfilehash: 4cf0fbcbf6af53c6a7865e2a2cf7874ea44581e4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474617"
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="4ef70-102">ISymUnmanagedWriter::OpenNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="4ef70-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>
<span data-ttu-id="4ef70-103">Öffnet einen neuen Namespace.</span><span class="sxs-lookup"><span data-stu-id="4ef70-103">Opens a new namespace.</span></span> <span data-ttu-id="4ef70-104">Rufen Sie diese Methode vor dem Definieren von Methoden und Variablen, die einen Namespace zu belegen.</span><span class="sxs-lookup"><span data-stu-id="4ef70-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="4ef70-105">Namespaces können geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="4ef70-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ef70-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="4ef70-106">Syntax</span></span>  
  
```  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ef70-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="4ef70-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="4ef70-108">[in] Ein Zeiger auf den Namen des neuen Namespaces.</span><span class="sxs-lookup"><span data-stu-id="4ef70-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4ef70-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4ef70-109">Return Value</span></span>  
 <span data-ttu-id="4ef70-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="4ef70-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ef70-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4ef70-111">Requirements</span></span>  
 <span data-ttu-id="4ef70-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4ef70-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ef70-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ef70-113">See also</span></span>
- [<span data-ttu-id="4ef70-114">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4ef70-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="4ef70-115">CloseNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="4ef70-115">CloseNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)
