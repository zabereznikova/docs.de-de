---
title: ISymENCUnmanagedMethod::GetDocumentsForMethod-Methode
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetDocumentsForMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethod
helpviewer_keywords:
- GetDocumentsForMethod method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethod method [.NET Framework debugging]
ms.assetid: bd6ccde5-d578-48d8-abed-b474fbd48d13
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8efcd62f39a7de397ef93231fd125a17c7e513e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425076"
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a><span data-ttu-id="df7a8-102">ISymENCUnmanagedMethod::GetDocumentsForMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="df7a8-102">ISymENCUnmanagedMethod::GetDocumentsForMethod Method</span></span>
<span data-ttu-id="df7a8-103">Ruft die Dokumente, die diese Methode in Zeilen umfasst.</span><span class="sxs-lookup"><span data-stu-id="df7a8-103">Gets the documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df7a8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="df7a8-104">Syntax</span></span>  
  
```  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,   
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="df7a8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="df7a8-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="df7a8-106">[in] Die Länge des Puffers verweist `pcDocs`.</span><span class="sxs-lookup"><span data-stu-id="df7a8-106">[in] The length of the buffer pointed to by `pcDocs`.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="df7a8-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe des für die Dokumente enthalten alle erforderlichen Puffers in Zeichen.</span><span class="sxs-lookup"><span data-stu-id="df7a8-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the documents.</span></span>  
  
 `documents`  
 <span data-ttu-id="df7a8-108">[in] Der Puffer, der die Dokumente enthält.</span><span class="sxs-lookup"><span data-stu-id="df7a8-108">[in] The buffer that contains the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df7a8-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="df7a8-109">Return Value</span></span>  
 <span data-ttu-id="df7a8-110">S_OK, wenn die Methode erfolgreich ist; andernfalls ein Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="df7a8-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df7a8-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="df7a8-111">Requirements</span></span>  
 <span data-ttu-id="df7a8-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="df7a8-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df7a8-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df7a8-113">See Also</span></span>  
 [<span data-ttu-id="df7a8-114">ISymENCUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="df7a8-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
