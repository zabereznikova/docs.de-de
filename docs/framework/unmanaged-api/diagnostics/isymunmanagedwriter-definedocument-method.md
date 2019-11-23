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
ms.openlocfilehash: 02b270677131d0960db67b0ac8db38cba2b5e2df
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428057"
---
# <a name="isymunmanagedwriterdefinedocument-method"></a><span data-ttu-id="48305-102">ISymUnmanagedWriter::DefineDocument-Methode</span><span class="sxs-lookup"><span data-stu-id="48305-102">ISymUnmanagedWriter::DefineDocument Method</span></span>
<span data-ttu-id="48305-103">Definiert ein Quelldokument.</span><span class="sxs-lookup"><span data-stu-id="48305-103">Defines a source document.</span></span> <span data-ttu-id="48305-104">GUIDs are provided for known languages, vendors, and document types.</span><span class="sxs-lookup"><span data-stu-id="48305-104">GUIDs are provided for known languages, vendors, and document types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48305-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="48305-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48305-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="48305-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="48305-107">[in] A pointer to a `WCHAR` that defines the uniform resource locator (URL) that identifies the document.</span><span class="sxs-lookup"><span data-stu-id="48305-107">[in] A pointer to a `WCHAR` that defines the uniform resource locator (URL) that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="48305-108">[in] A pointer to a GUID that defines the document language.</span><span class="sxs-lookup"><span data-stu-id="48305-108">[in] A pointer to a GUID that defines the document language.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="48305-109">[in] A pointer to a GUID that defines the identity of the vendor for the document language.</span><span class="sxs-lookup"><span data-stu-id="48305-109">[in] A pointer to a GUID that defines the identity of the vendor for the document language.</span></span>  
  
 `documentType`  
 <span data-ttu-id="48305-110">[in] A pointer to a GUID that defines the type of the document.</span><span class="sxs-lookup"><span data-stu-id="48305-110">[in] A pointer to a GUID that defines the type of the document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="48305-111">[out] A pointer to the returned [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span><span class="sxs-lookup"><span data-stu-id="48305-111">[out] A pointer to the returned [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48305-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="48305-112">Return Value</span></span>  
 <span data-ttu-id="48305-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="48305-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48305-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="48305-114">Requirements</span></span>  
 <span data-ttu-id="48305-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="48305-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48305-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48305-116">See also</span></span>

- [<span data-ttu-id="48305-117">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="48305-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
