---
title: ISymENCUnmanagedMethod::GetDocumentsForMethodCount-Methode
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetDocumentsForMethodCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethodCount
helpviewer_keywords:
- GetDocumentsForMethodCount method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethodCount method [.NET Framework debugging]
ms.assetid: cc1a823a-3ff3-4a33-b641-96edc93d2b17
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f3c7f7e06822f419282209ac39d4cbd46e600a66
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424988"
---
# <a name="isymencunmanagedmethodgetdocumentsformethodcount-method"></a><span data-ttu-id="8d1c0-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount-Methode</span><span class="sxs-lookup"><span data-stu-id="8d1c0-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount Method</span></span>
<span data-ttu-id="8d1c0-103">Ruft die Anzahl der Dokumente, die diese Methode in Zeilen umfasst.</span><span class="sxs-lookup"><span data-stu-id="8d1c0-103">Gets the number of documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d1c0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8d1c0-104">Syntax</span></span>  
  
```  
HRESULT GetDocumentsForMethodCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8d1c0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8d1c0-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="8d1c0-106">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe des Puffers erforderlich, um die Dokumente enthalten.</span><span class="sxs-lookup"><span data-stu-id="8d1c0-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8d1c0-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8d1c0-107">Return Value</span></span>  
 <span data-ttu-id="8d1c0-108">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="8d1c0-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d1c0-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8d1c0-109">Requirements</span></span>  
 <span data-ttu-id="8d1c0-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8d1c0-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d1c0-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8d1c0-111">See Also</span></span>  
 [<span data-ttu-id="8d1c0-112">ISymENCUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8d1c0-112">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
