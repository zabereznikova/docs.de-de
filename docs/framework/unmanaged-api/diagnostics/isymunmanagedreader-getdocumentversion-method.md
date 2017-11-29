---
title: ISymUnmanagedReader::GetDocumentVersion-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetDocumentVersion
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetDocumentVersion
helpviewer_keywords:
- GetDocumentVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocumentVersion method [.NET Framework debugging]
ms.assetid: a51f1f64-e084-44c5-830c-2222da5a6bbf
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 377457fa852e1a4ae140f72d2dd83731490b81d9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a><span data-ttu-id="8610d-102">ISymUnmanagedReader::GetDocumentVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="8610d-102">ISymUnmanagedReader::GetDocumentVersion Method</span></span>
<span data-ttu-id="8610d-103">Ruft die angegebene Version des angegebenen Dokuments ab.</span><span class="sxs-lookup"><span data-stu-id="8610d-103">Gets the specified version of the specified document.</span></span> <span data-ttu-id="8610d-104">Die Dokumentversion beginnt mit 1 und erhöht sich beim das Dokument aktualisiert wird, mit der [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="8610d-104">The document version starts at 1 and is incremented each time the document is updated using the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method.</span></span> <span data-ttu-id="8610d-105">Wenn die `pbCurrent` Parameter ist `true`, dies ist die neueste Version des Dokuments.</span><span class="sxs-lookup"><span data-stu-id="8610d-105">If the `pbCurrent` parameter is `true`, this is the latest version of the document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8610d-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="8610d-106">Syntax</span></span>  
  
```  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8610d-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="8610d-107">Parameters</span></span>  
 `pDoc`  
 <span data-ttu-id="8610d-108">[in] Das angegebene Dokument.</span><span class="sxs-lookup"><span data-stu-id="8610d-108">[in] The specified document.</span></span>  
  
 `version`  
 <span data-ttu-id="8610d-109">[out] Ein Zeiger auf eine Variable, die Version des angegebenen Dokuments empfängt.</span><span class="sxs-lookup"><span data-stu-id="8610d-109">[out] A pointer to a variable that receives the version of the specified document.</span></span>  
  
 `pbCurrent`  
 <span data-ttu-id="8610d-110">[out] Ein Zeiger auf eine Variable, empfängt `true` ist dies die neueste Version des Dokuments oder `false` Falls sie nicht die neueste Version ist.</span><span class="sxs-lookup"><span data-stu-id="8610d-110">[out] A pointer to a variable that receives `true` if this is the latest version of the document, or `false` if it isn't the latest version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8610d-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8610d-111">Return Value</span></span>  
 <span data-ttu-id="8610d-112">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="8610d-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8610d-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8610d-113">Requirements</span></span>  
 <span data-ttu-id="8610d-114">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8610d-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8610d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8610d-115">See Also</span></span>  
 [<span data-ttu-id="8610d-116">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8610d-116">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
