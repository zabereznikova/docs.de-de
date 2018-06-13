---
title: ISymUnmanagedDocument::GetDocumentType-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetDocumentType
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetDocumentType
helpviewer_keywords:
- ISymUnmanagedDocument::GetDocumentType method [.NET Framework debugging]
- GetDocumentType method [.NET Framework debugging]
ms.assetid: 2d381ab1-7e7c-4281-af2b-e54d879b3ef8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0460086874af38cad348c965237f8c423f18e868
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435995"
---
# <a name="isymunmanageddocumentgetdocumenttype-method"></a><span data-ttu-id="d70d5-102">ISymUnmanagedDocument::GetDocumentType-Methode</span><span class="sxs-lookup"><span data-stu-id="d70d5-102">ISymUnmanagedDocument::GetDocumentType Method</span></span>
<span data-ttu-id="d70d5-103">Ruft den Dokumenttyp dieses Dokuments ab.</span><span class="sxs-lookup"><span data-stu-id="d70d5-103">Gets the document type of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d70d5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d70d5-104">Syntax</span></span>  
  
```  
HRESULT GetDocumentType(  
    [out, retval] GUID*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d70d5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d70d5-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="d70d5-106">[out] Ein Zeiger auf eine Variable, die den Dokumenttyp empfängt.</span><span class="sxs-lookup"><span data-stu-id="d70d5-106">[out] Pointer to a variable that receives the document type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d70d5-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d70d5-107">Return Value</span></span>  
 <span data-ttu-id="d70d5-108">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="d70d5-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d70d5-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d70d5-109">See Also</span></span>  
 [<span data-ttu-id="d70d5-110">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d70d5-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
