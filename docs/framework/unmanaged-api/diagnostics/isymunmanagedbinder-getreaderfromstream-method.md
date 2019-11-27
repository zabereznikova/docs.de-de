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
ms.openlocfilehash: b1cb2bf3aa021ed738f7fad93fc4b86d97baf1e5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449383"
---
# <a name="isymunmanagedbindergetreaderfromstream-method"></a><span data-ttu-id="6d0a9-102">ISymUnmanagedBinder::GetReaderFromStream-Methode</span><span class="sxs-lookup"><span data-stu-id="6d0a9-102">ISymUnmanagedBinder::GetReaderFromStream Method</span></span>
<span data-ttu-id="6d0a9-103">Gibt bei einer Metadatenschnittstelle und einem Stream, der den Symbol Speicher enthält, die korrekte [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Struktur zurück, die die Debugsymbole aus dem angegebenen Symbol Speicher liest.</span><span class="sxs-lookup"><span data-stu-id="6d0a9-103">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d0a9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6d0a9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderFromStream(  
    [in]  IUnknown  *importer,  
    [in]  IStream   *pstream,  
    [out,retval] ISymUnmanagedReader **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d0a9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6d0a9-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="6d0a9-106">in Ein Zeiger auf die Schnittstelle für den Metadatenimport.</span><span class="sxs-lookup"><span data-stu-id="6d0a9-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `pstream`  
 <span data-ttu-id="6d0a9-107">in Ein Zeiger auf den Stream, der den Symbol Speicher enthält.</span><span class="sxs-lookup"><span data-stu-id="6d0a9-107">[in] A pointer to the stream that contains the symbol store.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="6d0a9-108">vorgenommen Ein Zeiger, der auf die zurückgegebene [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Schnittstelle festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="6d0a9-108">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6d0a9-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6d0a9-109">Return Value</span></span>  
 <span data-ttu-id="6d0a9-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="6d0a9-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d0a9-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6d0a9-111">Requirements</span></span>  
 <span data-ttu-id="6d0a9-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="6d0a9-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d0a9-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d0a9-113">See also</span></span>

- [<span data-ttu-id="6d0a9-114">ISymUnmanagedBinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6d0a9-114">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
