---
title: ISymUnmanagedReader::GetDocument-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocument
helpviewer_keywords:
- ISymUnmanagedReader::GetDocument method [.NET Framework debugging]
- GetDocument method [.NET Framework debugging]
ms.assetid: bb203853-6a6d-4027-b9e9-603a7f28b9d3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2a173c23ea33532f05e30d072677715e15d04018
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939476"
---
# <a name="isymunmanagedreadergetdocument-method"></a><span data-ttu-id="e8665-102">ISymUnmanagedReader::GetDocument-Methode</span><span class="sxs-lookup"><span data-stu-id="e8665-102">ISymUnmanagedReader::GetDocument Method</span></span>
<span data-ttu-id="e8665-103">Sucht ein Dokument an.</span><span class="sxs-lookup"><span data-stu-id="e8665-103">Finds a document.</span></span> <span data-ttu-id="e8665-104">Die Sprache des Dokuments, Hersteller und Typ sind optional.</span><span class="sxs-lookup"><span data-stu-id="e8665-104">The document language, vendor, and type are optional.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8665-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e8665-105">Syntax</span></span>  
  
```  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8665-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e8665-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="e8665-107">[in] Die URL, die das Dokument kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="e8665-107">[in] The URL that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="e8665-108">[in] Die Sprache des Dokuments.</span><span class="sxs-lookup"><span data-stu-id="e8665-108">[in] The document language.</span></span> <span data-ttu-id="e8665-109">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="e8665-109">This parameter is optional.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="e8665-110">[in] Die Identität des Herstellers für die Sprache des Dokuments.</span><span class="sxs-lookup"><span data-stu-id="e8665-110">[in] The identity of the vendor for the document language.</span></span> <span data-ttu-id="e8665-111">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="e8665-111">This parameter is optional.</span></span>  
  
 `documentType`  
 <span data-ttu-id="e8665-112">[in] Der Typ des Dokuments.</span><span class="sxs-lookup"><span data-stu-id="e8665-112">[in] The type of the document.</span></span> <span data-ttu-id="e8665-113">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="e8665-113">This parameter is optional.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="e8665-114">[out] Ein Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="e8665-114">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8665-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e8665-115">Return Value</span></span>  
 <span data-ttu-id="e8665-116">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="e8665-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8665-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e8665-117">Requirements</span></span>  
 <span data-ttu-id="e8665-118">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e8665-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8665-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8665-119">See also</span></span>

- [<span data-ttu-id="e8665-120">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e8665-120">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
