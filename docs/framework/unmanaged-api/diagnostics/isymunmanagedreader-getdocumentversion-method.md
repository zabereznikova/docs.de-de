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
ms.openlocfilehash: 31b550c7b3cec999b0420fbdc06582a24f420abe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425983"
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a><span data-ttu-id="fa2c8-102">ISymUnmanagedReader::GetDocumentVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="fa2c8-102">ISymUnmanagedReader::GetDocumentVersion Method</span></span>
<span data-ttu-id="fa2c8-103">Ruft die angegebene Version des angegebenen Dokuments ab.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-103">Gets the specified version of the specified document.</span></span> <span data-ttu-id="fa2c8-104">Die Dokumentversion beginnt mit 1 und erhöht sich beim das Dokument aktualisiert wird, mit der [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-104">The document version starts at 1 and is incremented each time the document is updated using the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method.</span></span> <span data-ttu-id="fa2c8-105">Wenn die `pbCurrent` Parameter ist `true`, dies ist die neueste Version des Dokuments.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-105">If the `pbCurrent` parameter is `true`, this is the latest version of the document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa2c8-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa2c8-106">Syntax</span></span>  
  
```  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fa2c8-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="fa2c8-107">Parameters</span></span>  
 `pDoc`  
 <span data-ttu-id="fa2c8-108">[in] Das angegebene Dokument.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-108">[in] The specified document.</span></span>  
  
 `version`  
 <span data-ttu-id="fa2c8-109">[out] Ein Zeiger auf eine Variable, die Version des angegebenen Dokuments empfängt.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-109">[out] A pointer to a variable that receives the version of the specified document.</span></span>  
  
 `pbCurrent`  
 <span data-ttu-id="fa2c8-110">[out] Ein Zeiger auf eine Variable, empfängt `true` ist dies die neueste Version des Dokuments oder `false` Falls sie nicht die neueste Version ist.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-110">[out] A pointer to a variable that receives `true` if this is the latest version of the document, or `false` if it isn't the latest version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa2c8-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fa2c8-111">Return Value</span></span>  
 <span data-ttu-id="fa2c8-112">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="fa2c8-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa2c8-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fa2c8-113">Requirements</span></span>  
 <span data-ttu-id="fa2c8-114">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fa2c8-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa2c8-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa2c8-115">See Also</span></span>  
 [<span data-ttu-id="fa2c8-116">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fa2c8-116">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
