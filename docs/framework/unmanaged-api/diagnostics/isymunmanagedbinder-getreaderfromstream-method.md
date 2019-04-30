---
title: ISymUnmanagedBinder::GetReaderFromStream-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder.GetReaderFromStream
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder::GetReaderFromStream
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderFromStream method [.NET Framework debugging]
- GetReaderFromStream method [.NET Framework debugging]
ms.assetid: aa38efd4-de7e-4482-a5d3-adc152093460
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 21e147860c6859ea23409de31fed972c4f2bb432
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940074"
---
# <a name="isymunmanagedbindergetreaderfromstream-method"></a><span data-ttu-id="82485-102">ISymUnmanagedBinder::GetReaderFromStream-Methode</span><span class="sxs-lookup"><span data-stu-id="82485-102">ISymUnmanagedBinder::GetReaderFromStream Method</span></span>
<span data-ttu-id="82485-103">Gibt bei Angabe einer Metadaten-Schnittstelle und ein Stream, der den Symbolspeicher enthält, die richtige [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Struktur, die die Debugsymbole Symbole aus dem angegebenen Symbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="82485-103">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82485-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="82485-104">Syntax</span></span>  
  
```  
HRESULT GetReaderFromStream(  
    [in]  IUnknown  *importer,  
    [in]  IStream   *pstream,  
    [out,retval] ISymUnmanagedReader **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82485-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="82485-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="82485-106">[in] Ein Zeiger auf die Metadatenimport-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="82485-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `pstream`  
 <span data-ttu-id="82485-107">[in] Ein Zeiger auf den Stream, der den Symbolspeicher enthält.</span><span class="sxs-lookup"><span data-stu-id="82485-107">[in] A pointer to the stream that contains the symbol store.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="82485-108">[out] Ein Zeiger, der festgelegt ist auf das zurückgegebene [ISymUnmanagedReader](isymunmanagedreader-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="82485-108">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82485-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="82485-109">Return Value</span></span>  
 <span data-ttu-id="82485-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="82485-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82485-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="82485-111">Requirements</span></span>  
 <span data-ttu-id="82485-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="82485-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82485-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82485-113">See also</span></span>

- [<span data-ttu-id="82485-114">ISymUnmanagedBinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="82485-114">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
