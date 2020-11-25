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
ms.openlocfilehash: 53897b6f964afb1f8ca95bc8f93c532e148ad129
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730512"
---
# <a name="isymencunmanagedmethodgetdocumentsformethodcount-method"></a><span data-ttu-id="7eed4-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount-Methode</span><span class="sxs-lookup"><span data-stu-id="7eed4-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount Method</span></span>

<span data-ttu-id="7eed4-103">Ruft die Anzahl der Dokumente ab, in denen diese Methode Zeilen aufweist.</span><span class="sxs-lookup"><span data-stu-id="7eed4-103">Gets the number of documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7eed4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7eed4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethodCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7eed4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7eed4-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="7eed4-106">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers empfängt, der zum enthalten der Dokumente erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="7eed4-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7eed4-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7eed4-107">Return Value</span></span>  

 <span data-ttu-id="7eed4-108">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="7eed4-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7eed4-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7eed4-109">Requirements</span></span>  

 <span data-ttu-id="7eed4-110">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="7eed4-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eed4-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7eed4-111">See also</span></span>

- [<span data-ttu-id="7eed4-112">ISymENCUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7eed4-112">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
