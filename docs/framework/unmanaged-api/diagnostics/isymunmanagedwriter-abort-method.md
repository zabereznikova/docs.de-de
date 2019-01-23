---
title: ISymUnmanagedWriter::Abort-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Abort
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Abort
helpviewer_keywords:
- ISymUnmanagedWriter::Abort method [.NET Framework debugging]
- Abort method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 416b220f-38d4-48e0-bb49-d2faa7366702
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b4c79cb3df37a9ed10e46567be63aad29fee37c4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550187"
---
# <a name="isymunmanagedwriterabort-method"></a><span data-ttu-id="9ea6a-102">ISymUnmanagedWriter::Abort-Methode</span><span class="sxs-lookup"><span data-stu-id="9ea6a-102">ISymUnmanagedWriter::Abort Method</span></span>
<span data-ttu-id="9ea6a-103">Schließt den Symbolwriter ohne Commit für die Symbole an den Symbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="9ea6a-103">Closes the symbol writer without committing the symbols to the symbol store.</span></span> <span data-ttu-id="9ea6a-104">Nach dem Aufruf für der Symbolwriter weitere Updates ungültig wird.</span><span class="sxs-lookup"><span data-stu-id="9ea6a-104">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="9ea6a-105">Um einen commit der Symbole, und schließen den Symbolwriter, verwenden Sie die [ISymUnmanagedWriter:: Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="9ea6a-105">To commit the symbols and close the symbol writer, use the [ISymUnmanagedWriter::Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ea6a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9ea6a-106">Syntax</span></span>  
  
```  
HRESULT Abort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9ea6a-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9ea6a-107">Return Value</span></span>  
 <span data-ttu-id="9ea6a-108">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="9ea6a-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ea6a-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9ea6a-109">Requirements</span></span>  
 <span data-ttu-id="9ea6a-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9ea6a-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ea6a-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ea6a-111">See also</span></span>
- [<span data-ttu-id="9ea6a-112">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9ea6a-112">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
