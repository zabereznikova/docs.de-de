---
title: ISymUnmanagedWriter::Abort-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.Abort
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::Abort
helpviewer_keywords:
- ISymUnmanagedWriter::Abort method [.NET Framework debugging]
- Abort method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 416b220f-38d4-48e0-bb49-d2faa7366702
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 29dd11972e8db80f36820bba1eb679070d02146e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriterabort-method"></a><span data-ttu-id="84c66-102">ISymUnmanagedWriter::Abort-Methode</span><span class="sxs-lookup"><span data-stu-id="84c66-102">ISymUnmanagedWriter::Abort Method</span></span>
<span data-ttu-id="84c66-103">Schließt den Symbolwriter ohne dass die Symbole an den Symbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="84c66-103">Closes the symbol writer without committing the symbols to the symbol store.</span></span> <span data-ttu-id="84c66-104">Nach diesem Aufruf wird der Symbolwriter für weitere Updates ungültig.</span><span class="sxs-lookup"><span data-stu-id="84c66-104">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="84c66-105">Um einen commit der Symbole, und schließen den Symbolwriter, verwenden die [ISymUnmanagedWriter:: Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="84c66-105">To commit the symbols and close the symbol writer, use the [ISymUnmanagedWriter::Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84c66-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="84c66-106">Syntax</span></span>  
  
```  
HRESULT Abort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="84c66-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="84c66-107">Return Value</span></span>  
 <span data-ttu-id="84c66-108">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="84c66-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84c66-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="84c66-109">Requirements</span></span>  
 <span data-ttu-id="84c66-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="84c66-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84c66-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84c66-111">See Also</span></span>  
 [<span data-ttu-id="84c66-112">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84c66-112">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
