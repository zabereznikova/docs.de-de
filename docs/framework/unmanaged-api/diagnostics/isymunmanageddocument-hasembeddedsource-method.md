---
title: ISymUnmanagedDocument::HasEmbeddedSource-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.HasEmbeddedSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::HasEmbeddedSource
helpviewer_keywords:
- HasEmbeddedSource method [.NET Framework debugging]
- ISymUnmanagedDocument::HasEmbeddedSource method [.NET Framework debugging]
ms.assetid: 385fc4d3-365c-4645-b7b0-6c4c5344b79f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d6c79be95ff80c8de9b07cb33be46a5f5db22b1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939801"
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a><span data-ttu-id="2305a-102">ISymUnmanagedDocument::HasEmbeddedSource-Methode</span><span class="sxs-lookup"><span data-stu-id="2305a-102">ISymUnmanagedDocument::HasEmbeddedSource Method</span></span>
<span data-ttu-id="2305a-103">Gibt `true` verfügt das Dokument Quelle eingebettet, die in den Debugsymbolen; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="2305a-103">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2305a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2305a-104">Syntax</span></span>  
  
```  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2305a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2305a-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="2305a-106">[out] Ein Zeiger auf eine Variable, die angibt, ob das Dokument in den Debugsymbolen eingebettete Quelle verfügt.</span><span class="sxs-lookup"><span data-stu-id="2305a-106">[out] A pointer to a variable that indicates whether the document has source embedded in the debugging symbols.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2305a-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2305a-107">Return Value</span></span>  
 <span data-ttu-id="2305a-108">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="2305a-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2305a-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2305a-109">See also</span></span>

- [<span data-ttu-id="2305a-110">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2305a-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
