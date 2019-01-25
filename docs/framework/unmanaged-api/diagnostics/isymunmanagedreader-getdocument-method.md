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
ms.openlocfilehash: ecd11b57d1901c4618ee0d27442753559b85c509
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54738104"
---
# <a name="isymunmanagedreadergetdocument-method"></a><span data-ttu-id="e1102-102">ISymUnmanagedReader::GetDocument-Methode</span><span class="sxs-lookup"><span data-stu-id="e1102-102">ISymUnmanagedReader::GetDocument Method</span></span>
<span data-ttu-id="e1102-103">Sucht ein Dokument an.</span><span class="sxs-lookup"><span data-stu-id="e1102-103">Finds a document.</span></span> <span data-ttu-id="e1102-104">Die Sprache des Dokuments, Hersteller und Typ sind optional.</span><span class="sxs-lookup"><span data-stu-id="e1102-104">The document language, vendor, and type are optional.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1102-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e1102-105">Syntax</span></span>  
  
```  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e1102-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e1102-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="e1102-107">[in] Die URL, die das Dokument kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="e1102-107">[in] The URL that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="e1102-108">[in] Die Sprache des Dokuments.</span><span class="sxs-lookup"><span data-stu-id="e1102-108">[in] The document language.</span></span> <span data-ttu-id="e1102-109">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="e1102-109">This parameter is optional.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="e1102-110">[in] Die Identität des Herstellers für die Sprache des Dokuments.</span><span class="sxs-lookup"><span data-stu-id="e1102-110">[in] The identity of the vendor for the document language.</span></span> <span data-ttu-id="e1102-111">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="e1102-111">This parameter is optional.</span></span>  
  
 `documentType`  
 <span data-ttu-id="e1102-112">[in] Der Typ des Dokuments.</span><span class="sxs-lookup"><span data-stu-id="e1102-112">[in] The type of the document.</span></span> <span data-ttu-id="e1102-113">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="e1102-113">This parameter is optional.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="e1102-114">[out] Ein Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="e1102-114">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e1102-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e1102-115">Return Value</span></span>  
 <span data-ttu-id="e1102-116">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="e1102-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1102-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e1102-117">Requirements</span></span>  
 <span data-ttu-id="e1102-118">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e1102-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1102-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1102-119">See also</span></span>
- [<span data-ttu-id="e1102-120">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e1102-120">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
