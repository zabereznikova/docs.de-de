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
ms.openlocfilehash: 97f0d81c389ffd0bd8a69df2ca39322d726f98bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176629"
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a><span data-ttu-id="08840-102">ISymENCUnmanagedMethod::GetDocumentsForMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="08840-102">ISymENCUnmanagedMethod::GetDocumentsForMethod Method</span></span>
<span data-ttu-id="08840-103">Ruft die Dokumente ab, in denen diese Methode Zeilen enthält.</span><span class="sxs-lookup"><span data-stu-id="08840-103">Gets the documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08840-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="08840-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08840-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="08840-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="08840-106">[in] Die Länge des Puffers, auf den von `pcDocs`verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="08840-106">[in] The length of the buffer pointed to by `pcDocs`.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="08840-107">[out] Ein Zeiger auf `ULONG32` eine, der die Größe des Puffers in Zeichen empfängt, der erforderlich ist, um die Dokumente zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="08840-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the documents.</span></span>  
  
 `documents`  
 <span data-ttu-id="08840-108">[in] Der Puffer, der die Dokumente enthält.</span><span class="sxs-lookup"><span data-stu-id="08840-108">[in] The buffer that contains the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08840-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="08840-109">Return Value</span></span>  
 <span data-ttu-id="08840-110">S_OK, ob die Methode erfolgreich ist. andernfalls ein Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="08840-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08840-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="08840-111">Requirements</span></span>  
 <span data-ttu-id="08840-112">**Kopfzeile:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="08840-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08840-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="08840-113">See also</span></span>

- [<span data-ttu-id="08840-114">ISymENCUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08840-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
