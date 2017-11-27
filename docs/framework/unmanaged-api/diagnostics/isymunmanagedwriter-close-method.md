---
title: ISymUnmanagedWriter::Close-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.Close
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::Close
helpviewer_keywords:
- Close method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::Close method [.NET Framework debugging]
ms.assetid: 4cce59e1-80b9-4fc4-b3aa-126f1c5876bc
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ad0cec59531a7e22d0a4d2220cb2dfcdd8f27596
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriterclose-method"></a><span data-ttu-id="6d812-102">ISymUnmanagedWriter::Close-Methode</span><span class="sxs-lookup"><span data-stu-id="6d812-102">ISymUnmanagedWriter::Close Method</span></span>
<span data-ttu-id="6d812-103">Schließt den Symbolwriter nach dem Ausführen eines Commits für die Symbole an den Symbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="6d812-103">Closes the symbol writer after committing the symbols to the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d812-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6d812-104">Syntax</span></span>  
  
```  
HRESULT Close();  
```  
  
## <a name="return-value"></a><span data-ttu-id="6d812-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6d812-105">Return Value</span></span>  
 <span data-ttu-id="6d812-106">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="6d812-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d812-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6d812-107">Remarks</span></span>  
 <span data-ttu-id="6d812-108">Nach diesem Aufruf wird der Symbolwriter für weitere Updates ungültig.</span><span class="sxs-lookup"><span data-stu-id="6d812-108">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="6d812-109">Um den Symbolwriter zu schließen, ohne dass die Symbole verwenden die [ISymUnmanagedWriter:: Abort](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="6d812-109">To close the symbol writer without committing the symbols, use the [ISymUnmanagedWriter::Abort](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md) method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d812-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6d812-110">Requirements</span></span>  
 <span data-ttu-id="6d812-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6d812-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d812-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d812-112">See Also</span></span>  
 [<span data-ttu-id="6d812-113">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6d812-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
