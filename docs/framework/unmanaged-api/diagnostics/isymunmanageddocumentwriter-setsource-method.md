---
title: ISymUnmanagedDocumentWriter::SetSource-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocumentWriter.SetSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocumentWriter::SetSource
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetSource method [.NET Framework debugging]
- SetSource method [.NET Framework debugging]
ms.assetid: ea5b9d9f-ff06-4bd3-8de5-6435343aba59
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bcdda6f8cdd0fc0b333b81d58a8bff7c21aa1fef
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486406"
---
# <a name="isymunmanageddocumentwritersetsource-method"></a><span data-ttu-id="ccf9e-102">ISymUnmanagedDocumentWriter::SetSource-Methode</span><span class="sxs-lookup"><span data-stu-id="ccf9e-102">ISymUnmanagedDocumentWriter::SetSource Method</span></span>
<span data-ttu-id="ccf9e-103">Legt die eingebettete Quelle für ein Dokument, das geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="ccf9e-103">Sets embedded source for a document that is being written.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccf9e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ccf9e-104">Syntax</span></span>  
  
```  
HRESULT SetSource(  
    [in]  ULONG32  sourceSize,  
    [in, size_is(sourceSize)] BYTE  source[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccf9e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ccf9e-105">Parameters</span></span>  
 `sourceSize`  
 <span data-ttu-id="ccf9e-106">[in] Ein `ULONG32` , enthält die Größe der `source` Puffer.</span><span class="sxs-lookup"><span data-stu-id="ccf9e-106">[in] A `ULONG32` that contains the size of the `source` buffer.</span></span>  
  
 `source`  
 <span data-ttu-id="ccf9e-107">[in] Der Puffer, der die eingebettete Quelle gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ccf9e-107">[in] The buffer that stores the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ccf9e-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ccf9e-108">Return Value</span></span>  
 <span data-ttu-id="ccf9e-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="ccf9e-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccf9e-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ccf9e-110">Requirements</span></span>  
 <span data-ttu-id="ccf9e-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ccf9e-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccf9e-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ccf9e-112">See also</span></span>
- [<span data-ttu-id="ccf9e-113">ISymUnmanagedDocumentWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ccf9e-113">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)
