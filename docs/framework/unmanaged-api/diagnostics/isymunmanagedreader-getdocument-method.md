---
title: ISymUnmanagedReader::GetDocument-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetDocument
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetDocument
helpviewer_keywords:
- ISymUnmanagedReader::GetDocument method [.NET Framework debugging]
- GetDocument method [.NET Framework debugging]
ms.assetid: bb203853-6a6d-4027-b9e9-603a7f28b9d3
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 00ded0e7e88cacbcedb66e1cef27e4f5eaaf4d29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetdocument-method"></a><span data-ttu-id="6bb36-102">ISymUnmanagedReader::GetDocument-Methode</span><span class="sxs-lookup"><span data-stu-id="6bb36-102">ISymUnmanagedReader::GetDocument Method</span></span>
<span data-ttu-id="6bb36-103">Sucht nach einem Dokument.</span><span class="sxs-lookup"><span data-stu-id="6bb36-103">Finds a document.</span></span> <span data-ttu-id="6bb36-104">Die Dokumentsprache, Hersteller und Typ sind optional.</span><span class="sxs-lookup"><span data-stu-id="6bb36-104">The document language, vendor, and type are optional.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bb36-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6bb36-105">Syntax</span></span>  
  
```  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6bb36-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="6bb36-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="6bb36-107">[in] Die URL, die das Dokument kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="6bb36-107">[in] The URL that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="6bb36-108">[in] Die Dokumentsprache.</span><span class="sxs-lookup"><span data-stu-id="6bb36-108">[in] The document language.</span></span> <span data-ttu-id="6bb36-109">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="6bb36-109">This parameter is optional.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="6bb36-110">[in] Die Identität des Herstellers für die Dokumentsprache.</span><span class="sxs-lookup"><span data-stu-id="6bb36-110">[in] The identity of the vendor for the document language.</span></span> <span data-ttu-id="6bb36-111">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="6bb36-111">This parameter is optional.</span></span>  
  
 `documentType`  
 <span data-ttu-id="6bb36-112">[in] Der Typ des Dokuments.</span><span class="sxs-lookup"><span data-stu-id="6bb36-112">[in] The type of the document.</span></span> <span data-ttu-id="6bb36-113">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="6bb36-113">This parameter is optional.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="6bb36-114">[out] Ein Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="6bb36-114">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6bb36-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6bb36-115">Return Value</span></span>  
 <span data-ttu-id="6bb36-116">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="6bb36-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bb36-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6bb36-117">Requirements</span></span>  
 <span data-ttu-id="6bb36-118">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6bb36-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bb36-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6bb36-119">See Also</span></span>  
 [<span data-ttu-id="6bb36-120">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6bb36-120">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
