---
title: ISymUnmanagedDocument::HasEmbeddedSource-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f2a903974ac5ac4182bb6fa1664d0c5954cefdb0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a><span data-ttu-id="cf173-102">ISymUnmanagedDocument::HasEmbeddedSource-Methode</span><span class="sxs-lookup"><span data-stu-id="cf173-102">ISymUnmanagedDocument::HasEmbeddedSource Method</span></span>
<span data-ttu-id="cf173-103">Gibt `true` , wenn das Dokument die Quelle in den Debugsymbolen; eingebettet ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="cf173-103">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf173-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf173-104">Syntax</span></span>  
  
```  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cf173-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cf173-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="cf173-106">[out] Ein Zeiger auf eine Variable, die angibt, ob das Dokument in den Debugsymbolen eingebettete Quelle hat.</span><span class="sxs-lookup"><span data-stu-id="cf173-106">[out] A pointer to a variable that indicates whether the document has source embedded in the debugging symbols.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf173-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cf173-107">Return Value</span></span>  
 <span data-ttu-id="cf173-108">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="cf173-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf173-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf173-109">See Also</span></span>  
 [<span data-ttu-id="cf173-110">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cf173-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
