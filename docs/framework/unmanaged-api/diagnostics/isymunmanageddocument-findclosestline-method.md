---
title: ISymUnmanagedDocument::FindClosestLine-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.FindClosestLine
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::FindClosestLine
helpviewer_keywords:
- FindClosestLine method [.NET Framework debugging]
- ISymUnmanagedDocument::FindClosestLine method [.NET Framework debugging]
ms.assetid: 628f2a04-e529-407d-841e-3b3da219a9cb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ab7df9b77b1820f291c1b1873b4dfb39e326bc34
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939931"
---
# <a name="isymunmanageddocumentfindclosestline-method"></a><span data-ttu-id="80f1d-102">ISymUnmanagedDocument::FindClosestLine-Methode</span><span class="sxs-lookup"><span data-stu-id="80f1d-102">ISymUnmanagedDocument::FindClosestLine Method</span></span>
<span data-ttu-id="80f1d-103">Gibt die nächste Zeile, die ein Sequenzpunkt ist, ausgehend von einer Zeile in diesem Dokument, das nicht unbedingt ein Sequenzpunkt zurück.</span><span class="sxs-lookup"><span data-stu-id="80f1d-103">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80f1d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="80f1d-104">Syntax</span></span>  
  
```  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80f1d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="80f1d-105">Parameters</span></span>  
 `line`  
 <span data-ttu-id="80f1d-106">[in] Eine Zeile in diesem Dokument.</span><span class="sxs-lookup"><span data-stu-id="80f1d-106">[in] A line in this document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="80f1d-107">[out] Ein Zeiger auf eine Variable, die Zeile empfängt.</span><span class="sxs-lookup"><span data-stu-id="80f1d-107">[out] A pointer to a variable that receives the line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80f1d-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="80f1d-108">Return Value</span></span>  
 <span data-ttu-id="80f1d-109">S_OK, wenn die Methode erfolgreich ist; andernfalls ein Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="80f1d-109">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80f1d-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80f1d-110">See also</span></span>

- [<span data-ttu-id="80f1d-111">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="80f1d-111">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
