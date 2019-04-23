---
title: ISymUnmanagedReader::GetDocumentVersion-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocumentVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocumentVersion
helpviewer_keywords:
- GetDocumentVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocumentVersion method [.NET Framework debugging]
ms.assetid: a51f1f64-e084-44c5-830c-2222da5a6bbf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 92353cfc2d9ce39074bf43937b5673ff51e34822
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080006"
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a><span data-ttu-id="69a73-102">ISymUnmanagedReader::GetDocumentVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="69a73-102">ISymUnmanagedReader::GetDocumentVersion Method</span></span>
<span data-ttu-id="69a73-103">Ruft die angegebene Version des angegebenen Dokuments ab.</span><span class="sxs-lookup"><span data-stu-id="69a73-103">Gets the specified version of the specified document.</span></span> <span data-ttu-id="69a73-104">Die Version beginnt bei 1 und wird erhöht, jeder Aktualisierung des Dokuments wird mithilfe der [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="69a73-104">The document version starts at 1 and is incremented each time the document is updated using the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method.</span></span> <span data-ttu-id="69a73-105">Wenn die `pbCurrent` Parameter `true`, dies ist die neueste Version des Dokuments.</span><span class="sxs-lookup"><span data-stu-id="69a73-105">If the `pbCurrent` parameter is `true`, this is the latest version of the document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69a73-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="69a73-106">Syntax</span></span>  
  
```  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69a73-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="69a73-107">Parameters</span></span>  
 `pDoc`  
 <span data-ttu-id="69a73-108">[in] Das angegebene Dokument.</span><span class="sxs-lookup"><span data-stu-id="69a73-108">[in] The specified document.</span></span>  
  
 `version`  
 <span data-ttu-id="69a73-109">[out] Ein Zeiger auf eine Variable, die Version des angegebenen Dokuments empfängt.</span><span class="sxs-lookup"><span data-stu-id="69a73-109">[out] A pointer to a variable that receives the version of the specified document.</span></span>  
  
 `pbCurrent`  
 <span data-ttu-id="69a73-110">[out] Ein Zeiger auf eine Variable, empfängt `true` ist dies die neueste Version des Dokuments oder `false` Falls sie nicht, dass die neueste Version ist.</span><span class="sxs-lookup"><span data-stu-id="69a73-110">[out] A pointer to a variable that receives `true` if this is the latest version of the document, or `false` if it isn't the latest version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="69a73-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="69a73-111">Return Value</span></span>  
 <span data-ttu-id="69a73-112">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="69a73-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69a73-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="69a73-113">Requirements</span></span>  
 <span data-ttu-id="69a73-114">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="69a73-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69a73-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69a73-115">See also</span></span>

- [<span data-ttu-id="69a73-116">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="69a73-116">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
