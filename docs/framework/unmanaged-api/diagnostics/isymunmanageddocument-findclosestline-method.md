---
title: ISymUnmanagedDocument::FindClosestLine-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.FindClosestLine
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::FindClosestLine
helpviewer_keywords:
- FindClosestLine method [.NET Framework debugging]
- ISymUnmanagedDocument::FindClosestLine method [.NET Framework debugging]
ms.assetid: 628f2a04-e529-407d-841e-3b3da219a9cb
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a5467f7d500719e8849b85a57195e98c6eeb7fb3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumentfindclosestline-method"></a><span data-ttu-id="0db11-102">ISymUnmanagedDocument::FindClosestLine-Methode</span><span class="sxs-lookup"><span data-stu-id="0db11-102">ISymUnmanagedDocument::FindClosestLine Method</span></span>
<span data-ttu-id="0db11-103">Gibt die nächste Zeile, die ein Sequenzpunkt ist, wobei eine angegebene Zeile in diesem Dokument, das nicht unbedingt ein Sequenzpunkt zurück.</span><span class="sxs-lookup"><span data-stu-id="0db11-103">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0db11-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0db11-104">Syntax</span></span>  
  
```  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0db11-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0db11-105">Parameters</span></span>  
 `line`  
 <span data-ttu-id="0db11-106">[in] Eine Zeile in diesem Dokument.</span><span class="sxs-lookup"><span data-stu-id="0db11-106">[in] A line in this document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="0db11-107">[out] Ein Zeiger auf eine Variable, die Zeile empfängt.</span><span class="sxs-lookup"><span data-stu-id="0db11-107">[out] A pointer to a variable that receives the line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0db11-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0db11-108">Return Value</span></span>  
 <span data-ttu-id="0db11-109">S_OK, wenn die Methode erfolgreich ist; andernfalls ein Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="0db11-109">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0db11-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0db11-110">See Also</span></span>  
 [<span data-ttu-id="0db11-111">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0db11-111">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
