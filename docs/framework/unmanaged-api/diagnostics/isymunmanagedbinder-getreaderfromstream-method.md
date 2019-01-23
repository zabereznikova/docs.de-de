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
ms.openlocfilehash: af4e9124140c2b311fb2c10800200f5d4d8dc679
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54545763"
---
# <a name="isymunmanagedbindergetreaderfromstream-method"></a><span data-ttu-id="fd1d5-102">ISymUnmanagedBinder::GetReaderFromStream-Methode</span><span class="sxs-lookup"><span data-stu-id="fd1d5-102">ISymUnmanagedBinder::GetReaderFromStream Method</span></span>
<span data-ttu-id="fd1d5-103">Gibt bei Angabe einer Metadaten-Schnittstelle und ein Stream, der den Symbolspeicher enthält, die richtige [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Struktur, die die Debugsymbole Symbole aus dem angegebenen Symbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="fd1d5-103">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd1d5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd1d5-104">Syntax</span></span>  
  
```  
HRESULT GetReaderFromStream(  
    [in]  IUnknown  *importer,  
    [in]  IStream   *pstream,  
    [out,retval] ISymUnmanagedReader **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fd1d5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fd1d5-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="fd1d5-106">[in] Ein Zeiger auf die Metadatenimport-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="fd1d5-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `pstream`  
 <span data-ttu-id="fd1d5-107">[in] Ein Zeiger auf den Stream, der den Symbolspeicher enthält.</span><span class="sxs-lookup"><span data-stu-id="fd1d5-107">[in] A pointer to the stream that contains the symbol store.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="fd1d5-108">[out] Ein Zeiger, der festgelegt ist auf das zurückgegebene [ISymUnmanagedReader](isymunmanagedreader-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="fd1d5-108">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd1d5-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fd1d5-109">Return Value</span></span>  
 <span data-ttu-id="fd1d5-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="fd1d5-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd1d5-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fd1d5-111">Requirements</span></span>  
 <span data-ttu-id="fd1d5-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fd1d5-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd1d5-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd1d5-113">See also</span></span>
- [<span data-ttu-id="fd1d5-114">ISymUnmanagedBinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fd1d5-114">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
