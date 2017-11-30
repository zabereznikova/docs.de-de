---
title: ISymUnmanagedWriter::OpenNamespace-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.OpenNamespace
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::OpenNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::OpenNamespace method [.NET Framework debugging]
- OpenNamespace method [.NET Framework debugging]
ms.assetid: 426f4e4f-e60d-4ad1-b546-a10e3c55c283
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e3dffd9605bd238446156d7a32e8e668ddd80916
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="e8218-102">ISymUnmanagedWriter::OpenNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="e8218-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>
<span data-ttu-id="e8218-103">Öffnet einen neuen Namespace.</span><span class="sxs-lookup"><span data-stu-id="e8218-103">Opens a new namespace.</span></span> <span data-ttu-id="e8218-104">Rufen Sie diese Methode vor dem Definieren von Methoden und Variablen, die einen Namespace zu belegen.</span><span class="sxs-lookup"><span data-stu-id="e8218-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="e8218-105">Namespaces können geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="e8218-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8218-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e8218-106">Syntax</span></span>  
  
```  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e8218-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="e8218-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="e8218-108">[in] Ein Zeiger auf den Namen des neuen Namespaces.</span><span class="sxs-lookup"><span data-stu-id="e8218-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8218-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e8218-109">Return Value</span></span>  
 <span data-ttu-id="e8218-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="e8218-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8218-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e8218-111">Requirements</span></span>  
 <span data-ttu-id="e8218-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e8218-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8218-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8218-113">See Also</span></span>  
 [<span data-ttu-id="e8218-114">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e8218-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="e8218-115">CloseNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="e8218-115">CloseNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)
