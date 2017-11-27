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
ms.openlocfilehash: 7fcc18b1441093a3e3a1a0e813ccfb4ba3ad507b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetdocument-method"></a><span data-ttu-id="46dcf-102">ISymUnmanagedReader::GetDocument-Methode</span><span class="sxs-lookup"><span data-stu-id="46dcf-102">ISymUnmanagedReader::GetDocument Method</span></span>
<span data-ttu-id="46dcf-103">Sucht nach einem Dokument.</span><span class="sxs-lookup"><span data-stu-id="46dcf-103">Finds a document.</span></span> <span data-ttu-id="46dcf-104">Die Dokumentsprache, Hersteller und Typ sind optional.</span><span class="sxs-lookup"><span data-stu-id="46dcf-104">The document language, vendor, and type are optional.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46dcf-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="46dcf-105">Syntax</span></span>  
  
```  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="46dcf-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="46dcf-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="46dcf-107">[in] Die URL, die das Dokument kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="46dcf-107">[in] The URL that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="46dcf-108">[in] Die Dokumentsprache.</span><span class="sxs-lookup"><span data-stu-id="46dcf-108">[in] The document language.</span></span> <span data-ttu-id="46dcf-109">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="46dcf-109">This parameter is optional.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="46dcf-110">[in] Die Identität des Herstellers für die Dokumentsprache.</span><span class="sxs-lookup"><span data-stu-id="46dcf-110">[in] The identity of the vendor for the document language.</span></span> <span data-ttu-id="46dcf-111">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="46dcf-111">This parameter is optional.</span></span>  
  
 `documentType`  
 <span data-ttu-id="46dcf-112">[in] Der Typ des Dokuments.</span><span class="sxs-lookup"><span data-stu-id="46dcf-112">[in] The type of the document.</span></span> <span data-ttu-id="46dcf-113">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="46dcf-113">This parameter is optional.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="46dcf-114">[out] Ein Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="46dcf-114">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46dcf-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="46dcf-115">Return Value</span></span>  
 <span data-ttu-id="46dcf-116">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="46dcf-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46dcf-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="46dcf-117">Requirements</span></span>  
 <span data-ttu-id="46dcf-118">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="46dcf-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46dcf-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46dcf-119">See Also</span></span>  
 [<span data-ttu-id="46dcf-120">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="46dcf-120">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
