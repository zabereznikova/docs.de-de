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
ms.openlocfilehash: 09f39d3b6486e2ec3c04c5d1858a85ce56895527
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610157"
---
# <a name="isymunmanagedwriterabort-method"></a><span data-ttu-id="2c538-102">ISymUnmanagedWriter::Abort-Methode</span><span class="sxs-lookup"><span data-stu-id="2c538-102">ISymUnmanagedWriter::Abort Method</span></span>
<span data-ttu-id="2c538-103">Schließt den Symbolwriter, ohne die Symbole an den Symbol Speicher zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="2c538-103">Closes the symbol writer without committing the symbols to the symbol store.</span></span> <span data-ttu-id="2c538-104">Nach diesem Befehl wird der Symbolwriter für weitere Updates ungültig.</span><span class="sxs-lookup"><span data-stu-id="2c538-104">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="2c538-105">Verwenden Sie stattdessen die [ISymUnmanagedWriter:: Close](isymunmanagedwriter-close-method.md) -Methode, um ein Commit für die Symbole durchführen und den Symbolwriter zu schließen.</span><span class="sxs-lookup"><span data-stu-id="2c538-105">To commit the symbols and close the symbol writer, use the [ISymUnmanagedWriter::Close](isymunmanagedwriter-close-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c538-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c538-106">Syntax</span></span>  
  
```cpp  
HRESULT Abort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="2c538-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2c538-107">Return Value</span></span>  
 <span data-ttu-id="2c538-108">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="2c538-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c538-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2c538-109">Requirements</span></span>  
 <span data-ttu-id="2c538-110">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="2c538-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c538-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c538-111">See also</span></span>

- [<span data-ttu-id="2c538-112">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2c538-112">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
