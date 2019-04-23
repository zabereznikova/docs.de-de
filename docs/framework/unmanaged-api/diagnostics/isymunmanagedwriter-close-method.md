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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4d3497d3167715d3e8a04f10a6687260949e4a36
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104701"
---
# <a name="isymunmanagedwriterclose-method"></a><span data-ttu-id="50923-102">ISymUnmanagedWriter::Close-Methode</span><span class="sxs-lookup"><span data-stu-id="50923-102">ISymUnmanagedWriter::Close Method</span></span>
<span data-ttu-id="50923-103">Schließt den Symbolwriter nach dem Ausführen eines Commits für die Symbole an den Symbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="50923-103">Closes the symbol writer after committing the symbols to the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50923-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="50923-104">Syntax</span></span>  
  
```  
HRESULT Close();  
```  
  
## <a name="return-value"></a><span data-ttu-id="50923-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="50923-105">Return Value</span></span>  
 <span data-ttu-id="50923-106">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="50923-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50923-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="50923-107">Remarks</span></span>  
 <span data-ttu-id="50923-108">Nach dem Aufruf für der Symbolwriter weitere Updates ungültig wird.</span><span class="sxs-lookup"><span data-stu-id="50923-108">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="50923-109">Um den Symbolwriter schließen, ohne die Symbole zu übergeben, verwenden die [ISymUnmanagedWriter:: Abort](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="50923-109">To close the symbol writer without committing the symbols, use the [ISymUnmanagedWriter::Abort](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md) method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50923-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="50923-110">Requirements</span></span>  
 <span data-ttu-id="50923-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="50923-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50923-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50923-112">See also</span></span>

- [<span data-ttu-id="50923-113">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50923-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
