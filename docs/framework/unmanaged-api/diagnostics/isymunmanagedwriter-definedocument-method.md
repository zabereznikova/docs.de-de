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
ms.openlocfilehash: 6413935df86b85a959fa4f354c6233d18baf99d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727574"
---
# <a name="isymunmanagedwriterdefinedocument-method"></a><span data-ttu-id="850cb-102">ISymUnmanagedWriter::DefineDocument-Methode</span><span class="sxs-lookup"><span data-stu-id="850cb-102">ISymUnmanagedWriter::DefineDocument Method</span></span>

<span data-ttu-id="850cb-103">Definiert ein Quelldokument.</span><span class="sxs-lookup"><span data-stu-id="850cb-103">Defines a source document.</span></span> <span data-ttu-id="850cb-104">GUIDs werden für bekannte Sprachen, Anbieter und Dokumenttypen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="850cb-104">GUIDs are provided for known languages, vendors, and document types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="850cb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="850cb-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="850cb-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="850cb-106">Parameters</span></span>  

 `url`  
 <span data-ttu-id="850cb-107">in Ein Zeiger auf einen `WCHAR` , der die URL (Uniform Resource Serverlocatorpunkt) definiert, die das Dokument identifiziert.</span><span class="sxs-lookup"><span data-stu-id="850cb-107">[in] A pointer to a `WCHAR` that defines the uniform resource locator (URL) that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="850cb-108">in Ein Zeiger auf eine GUID, die die Dokument Sprache definiert.</span><span class="sxs-lookup"><span data-stu-id="850cb-108">[in] A pointer to a GUID that defines the document language.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="850cb-109">in Ein Zeiger auf eine GUID, die die Identität des Herstellers für die Dokument Sprache definiert.</span><span class="sxs-lookup"><span data-stu-id="850cb-109">[in] A pointer to a GUID that defines the identity of the vendor for the document language.</span></span>  
  
 `documentType`  
 <span data-ttu-id="850cb-110">in Ein Zeiger auf eine GUID, die den Typ des Dokuments definiert.</span><span class="sxs-lookup"><span data-stu-id="850cb-110">[in] A pointer to a GUID that defines the type of the document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="850cb-111">vorgenommen Ein Zeiger auf die zurückgegebene [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="850cb-111">[out] A pointer to the returned [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="850cb-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="850cb-112">Return Value</span></span>  

 <span data-ttu-id="850cb-113">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="850cb-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="850cb-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="850cb-114">Requirements</span></span>  

 <span data-ttu-id="850cb-115">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="850cb-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="850cb-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="850cb-116">See also</span></span>

- [<span data-ttu-id="850cb-117">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="850cb-117">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
