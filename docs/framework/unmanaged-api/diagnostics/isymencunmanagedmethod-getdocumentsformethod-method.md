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
ms.openlocfilehash: 49023424c21fced1c49b16ecdbea93c654b5e883
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448384"
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a><span data-ttu-id="11148-102">ISymENCUnmanagedMethod::GetDocumentsForMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="11148-102">ISymENCUnmanagedMethod::GetDocumentsForMethod Method</span></span>
<span data-ttu-id="11148-103">Ruft die Dokumente ab, in denen diese Methode Zeilen aufweist.</span><span class="sxs-lookup"><span data-stu-id="11148-103">Gets the documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11148-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="11148-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,   
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11148-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="11148-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="11148-106">in Die Länge des Puffers, auf den `pcDocs`zeigt.</span><span class="sxs-lookup"><span data-stu-id="11148-106">[in] The length of the buffer pointed to by `pcDocs`.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="11148-107">vorgenommen Ein Zeiger auf einen `ULONG32`, der die Größe des Puffers, der die Dokumente enthalten muss, in Zeichen empfängt.</span><span class="sxs-lookup"><span data-stu-id="11148-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the documents.</span></span>  
  
 `documents`  
 <span data-ttu-id="11148-108">in Der Puffer, der die Dokumente enthält.</span><span class="sxs-lookup"><span data-stu-id="11148-108">[in] The buffer that contains the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11148-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="11148-109">Return Value</span></span>  
 <span data-ttu-id="11148-110">S_OK, wenn die Methode erfolgreich ist. andernfalls ein Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="11148-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11148-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="11148-111">Requirements</span></span>  
 <span data-ttu-id="11148-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="11148-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11148-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11148-113">See also</span></span>

- [<span data-ttu-id="11148-114">ISymENCUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="11148-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
