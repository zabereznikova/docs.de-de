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
ms.openlocfilehash: 950fb3b9c51ae2c9470b5aadd31c877d7aa6b6f6
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615058"
---
# <a name="isymunmanagedreadergetdocument-method"></a><span data-ttu-id="af325-102">ISymUnmanagedReader::GetDocument-Methode</span><span class="sxs-lookup"><span data-stu-id="af325-102">ISymUnmanagedReader::GetDocument Method</span></span>
<span data-ttu-id="af325-103">Sucht ein Dokument.</span><span class="sxs-lookup"><span data-stu-id="af325-103">Finds a document.</span></span> <span data-ttu-id="af325-104">Die Dokument Sprache, der Anbieter und der Typ sind optional.</span><span class="sxs-lookup"><span data-stu-id="af325-104">The document language, vendor, and type are optional.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af325-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="af325-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af325-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="af325-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="af325-107">in Die URL, die das Dokument identifiziert.</span><span class="sxs-lookup"><span data-stu-id="af325-107">[in] The URL that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="af325-108">in Die Dokument Sprache.</span><span class="sxs-lookup"><span data-stu-id="af325-108">[in] The document language.</span></span> <span data-ttu-id="af325-109">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="af325-109">This parameter is optional.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="af325-110">in Die Identität des Herstellers für die Dokument Sprache.</span><span class="sxs-lookup"><span data-stu-id="af325-110">[in] The identity of the vendor for the document language.</span></span> <span data-ttu-id="af325-111">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="af325-111">This parameter is optional.</span></span>  
  
 `documentType`  
 <span data-ttu-id="af325-112">in Der Typ des Dokuments.</span><span class="sxs-lookup"><span data-stu-id="af325-112">[in] The type of the document.</span></span> <span data-ttu-id="af325-113">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="af325-113">This parameter is optional.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="af325-114">vorgenommen Ein Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="af325-114">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af325-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="af325-115">Return Value</span></span>  
 <span data-ttu-id="af325-116">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="af325-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af325-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="af325-117">Requirements</span></span>  
 <span data-ttu-id="af325-118">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="af325-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af325-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af325-119">See also</span></span>

- [<span data-ttu-id="af325-120">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="af325-120">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
