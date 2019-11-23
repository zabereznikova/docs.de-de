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
ms.openlocfilehash: 1fcb885b6e19457065c2ca9971f068b42f97147d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448343"
---
# <a name="isymunmanagedreadergetdocument-method"></a><span data-ttu-id="78ef7-102">ISymUnmanagedReader::GetDocument-Methode</span><span class="sxs-lookup"><span data-stu-id="78ef7-102">ISymUnmanagedReader::GetDocument Method</span></span>
<span data-ttu-id="78ef7-103">Finds a document.</span><span class="sxs-lookup"><span data-stu-id="78ef7-103">Finds a document.</span></span> <span data-ttu-id="78ef7-104">The document language, vendor, and type are optional.</span><span class="sxs-lookup"><span data-stu-id="78ef7-104">The document language, vendor, and type are optional.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78ef7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="78ef7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78ef7-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="78ef7-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="78ef7-107">[in] The URL that identifies the document.</span><span class="sxs-lookup"><span data-stu-id="78ef7-107">[in] The URL that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="78ef7-108">[in] The document language.</span><span class="sxs-lookup"><span data-stu-id="78ef7-108">[in] The document language.</span></span> <span data-ttu-id="78ef7-109">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="78ef7-109">This parameter is optional.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="78ef7-110">[in] The identity of the vendor for the document language.</span><span class="sxs-lookup"><span data-stu-id="78ef7-110">[in] The identity of the vendor for the document language.</span></span> <span data-ttu-id="78ef7-111">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="78ef7-111">This parameter is optional.</span></span>  
  
 `documentType`  
 <span data-ttu-id="78ef7-112">[in] The type of the document.</span><span class="sxs-lookup"><span data-stu-id="78ef7-112">[in] The type of the document.</span></span> <span data-ttu-id="78ef7-113">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="78ef7-113">This parameter is optional.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="78ef7-114">[out] A pointer to the returned interface.</span><span class="sxs-lookup"><span data-stu-id="78ef7-114">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="78ef7-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="78ef7-115">Return Value</span></span>  
 <span data-ttu-id="78ef7-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="78ef7-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78ef7-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="78ef7-117">Requirements</span></span>  
 <span data-ttu-id="78ef7-118">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="78ef7-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78ef7-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78ef7-119">See also</span></span>

- [<span data-ttu-id="78ef7-120">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="78ef7-120">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
