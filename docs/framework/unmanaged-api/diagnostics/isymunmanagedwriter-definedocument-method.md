---
title: ISymUnmanagedWriter::DefineDocument-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineDocument
helpviewer_keywords:
- ISymUnmanagedWriter::DefineDocument method [.NET Framework debugging]
- DefineDocument method [.NET Framework debugging]
ms.assetid: c3bf15b0-3250-4bbe-b9b5-c5d695289b6f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 726ac0e23f739f451e1a0ab66c4c36aa6edbe569
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934094"
---
# <a name="isymunmanagedwriterdefinedocument-method"></a><span data-ttu-id="eda2f-102">ISymUnmanagedWriter::DefineDocument-Methode</span><span class="sxs-lookup"><span data-stu-id="eda2f-102">ISymUnmanagedWriter::DefineDocument Method</span></span>
<span data-ttu-id="eda2f-103">Definiert ein Quelldokument.</span><span class="sxs-lookup"><span data-stu-id="eda2f-103">Defines a source document.</span></span> <span data-ttu-id="eda2f-104">GUIDs werden für bekannte Sprachen, Lieferanten und Dokumenttypen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="eda2f-104">GUIDs are provided for known languages, vendors, and document types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eda2f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="eda2f-105">Syntax</span></span>  
  
```  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eda2f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="eda2f-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="eda2f-107">[in] Ein Zeiger auf eine `WCHAR` , definiert den uniform Resource Locator (URL), die das Dokument kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="eda2f-107">[in] A pointer to a `WCHAR` that defines the uniform resource locator (URL) that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="eda2f-108">[in] Ein Zeiger auf eine GUID, die Sprache des Dokuments definiert.</span><span class="sxs-lookup"><span data-stu-id="eda2f-108">[in] A pointer to a GUID that defines the document language.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="eda2f-109">[in] Ein Zeiger auf eine GUID, die Identität des Herstellers für die Sprache des Dokuments definiert.</span><span class="sxs-lookup"><span data-stu-id="eda2f-109">[in] A pointer to a GUID that defines the identity of the vendor for the document language.</span></span>  
  
 `documentType`  
 <span data-ttu-id="eda2f-110">[in] Ein Zeiger auf eine GUID, die den Typ des Dokuments definiert.</span><span class="sxs-lookup"><span data-stu-id="eda2f-110">[in] A pointer to a GUID that defines the type of the document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="eda2f-111">[out] Ein Zeiger auf das zurückgegebene [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="eda2f-111">[out] A pointer to the returned [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eda2f-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="eda2f-112">Return Value</span></span>  
 <span data-ttu-id="eda2f-113">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="eda2f-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eda2f-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eda2f-114">Requirements</span></span>  
 <span data-ttu-id="eda2f-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="eda2f-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eda2f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eda2f-116">See also</span></span>

- [<span data-ttu-id="eda2f-117">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eda2f-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
