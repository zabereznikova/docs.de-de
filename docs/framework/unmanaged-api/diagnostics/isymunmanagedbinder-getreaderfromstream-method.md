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
ms.openlocfilehash: 4c5d3d1b868849d17b2068eecfcfeea0f1e598f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428516"
---
# <a name="isymunmanagedbindergetreaderfromstream-method"></a><span data-ttu-id="2c8e9-102">ISymUnmanagedBinder::GetReaderFromStream-Methode</span><span class="sxs-lookup"><span data-stu-id="2c8e9-102">ISymUnmanagedBinder::GetReaderFromStream Method</span></span>
<span data-ttu-id="2c8e9-103">Gibt bei Angabe einer Metadatenschnittstelle und einen Stream, der den Symbolspeicher enthält, den richtigen [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Struktur, die die Debugsymbole Symbole aus dem angegebenen Symbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="2c8e9-103">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c8e9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c8e9-104">Syntax</span></span>  
  
```  
HRESULT GetReaderFromStream(  
    [in]  IUnknown  *importer,  
    [in]  IStream   *pstream,  
    [out,retval] ISymUnmanagedReader **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2c8e9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2c8e9-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="2c8e9-106">[in] Ein Zeiger auf die Metadatenimport-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2c8e9-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `pstream`  
 <span data-ttu-id="2c8e9-107">[in] Ein Zeiger auf den Stream, der den Symbolspeicher enthält.</span><span class="sxs-lookup"><span data-stu-id="2c8e9-107">[in] A pointer to the stream that contains the symbol store.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="2c8e9-108">[out] Ein Zeiger, der festgelegt wird, wird auf das zurückgegebene [ISymUnmanagedReader](isymunmanagedreader-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2c8e9-108">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c8e9-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2c8e9-109">Return Value</span></span>  
 <span data-ttu-id="2c8e9-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="2c8e9-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c8e9-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2c8e9-111">Requirements</span></span>  
 <span data-ttu-id="2c8e9-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2c8e9-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c8e9-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c8e9-113">See Also</span></span>  
 [<span data-ttu-id="2c8e9-114">ISymUnmanagedBinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2c8e9-114">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
