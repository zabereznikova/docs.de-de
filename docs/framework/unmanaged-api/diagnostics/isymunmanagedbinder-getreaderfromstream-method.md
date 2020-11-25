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
ms.openlocfilehash: 2d927b02b7deebecb53a2218e2ec0275a07307b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706956"
---
# <a name="isymunmanagedbindergetreaderfromstream-method"></a><span data-ttu-id="22653-102">ISymUnmanagedBinder::GetReaderFromStream-Methode</span><span class="sxs-lookup"><span data-stu-id="22653-102">ISymUnmanagedBinder::GetReaderFromStream Method</span></span>

<span data-ttu-id="22653-103">Gibt bei einer Metadatenschnittstelle und einem Stream, der den Symbol Speicher enthält, die korrekte [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Struktur zurück, die die Debugsymbole aus dem angegebenen Symbol Speicher liest.</span><span class="sxs-lookup"><span data-stu-id="22653-103">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22653-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="22653-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderFromStream(  
    [in]  IUnknown  *importer,  
    [in]  IStream   *pstream,  
    [out,retval] ISymUnmanagedReader **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22653-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="22653-105">Parameters</span></span>  

 `importer`  
 <span data-ttu-id="22653-106">in Ein Zeiger auf die Schnittstelle für den Metadatenimport.</span><span class="sxs-lookup"><span data-stu-id="22653-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `pstream`  
 <span data-ttu-id="22653-107">in Ein Zeiger auf den Stream, der den Symbol Speicher enthält.</span><span class="sxs-lookup"><span data-stu-id="22653-107">[in] A pointer to the stream that contains the symbol store.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="22653-108">vorgenommen Ein Zeiger, der auf die zurückgegebene [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Schnittstelle festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="22653-108">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="22653-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="22653-109">Return Value</span></span>  

 <span data-ttu-id="22653-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="22653-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22653-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="22653-111">Requirements</span></span>  

 <span data-ttu-id="22653-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="22653-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22653-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="22653-113">See also</span></span>

- [<span data-ttu-id="22653-114">ISymUnmanagedBinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22653-114">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
