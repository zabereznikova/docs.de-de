---
title: ISymUnmanagedWriter::Close-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Close
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Close
helpviewer_keywords:
- Close method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::Close method [.NET Framework debugging]
ms.assetid: 4cce59e1-80b9-4fc4-b3aa-126f1c5876bc
topic_type:
- apiref
ms.openlocfilehash: 0a7ecd475a8031fedb2c8474593b45045fcc6fb9
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610131"
---
# <a name="isymunmanagedwriterclose-method"></a><span data-ttu-id="ea60d-102">ISymUnmanagedWriter::Close-Methode</span><span class="sxs-lookup"><span data-stu-id="ea60d-102">ISymUnmanagedWriter::Close Method</span></span>
<span data-ttu-id="ea60d-103">Schließt den Symbolwriter nach dem Commit der Symbole an den Symbol Speicher.</span><span class="sxs-lookup"><span data-stu-id="ea60d-103">Closes the symbol writer after committing the symbols to the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea60d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ea60d-104">Syntax</span></span>  
  
```cpp  
HRESULT Close();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ea60d-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ea60d-105">Return Value</span></span>  
 <span data-ttu-id="ea60d-106">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="ea60d-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea60d-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ea60d-107">Remarks</span></span>  
 <span data-ttu-id="ea60d-108">Nach diesem Befehl wird der Symbolwriter für weitere Updates ungültig.</span><span class="sxs-lookup"><span data-stu-id="ea60d-108">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="ea60d-109">Verwenden Sie stattdessen die [ISymUnmanagedWriter:: Abort](isymunmanagedwriter-abort-method.md) -Methode, um den Symbolwriter zu schließen, ohne die Symbole zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="ea60d-109">To close the symbol writer without committing the symbols, use the [ISymUnmanagedWriter::Abort](isymunmanagedwriter-abort-method.md) method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea60d-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ea60d-110">Requirements</span></span>  
 <span data-ttu-id="ea60d-111">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="ea60d-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea60d-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea60d-112">See also</span></span>

- [<span data-ttu-id="ea60d-113">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ea60d-113">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
