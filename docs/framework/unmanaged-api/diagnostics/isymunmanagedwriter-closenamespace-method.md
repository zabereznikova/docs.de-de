---
title: ISymUnmanagedWriter::CloseNamespace-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.CloseNamespace
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::CloseNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::CloseNamespace method [.NET Framework debugging]
- CloseNamespace method [.NET Framework debugging]
ms.assetid: 7f74d9c5-1377-4958-b842-6306d611cbd5
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8423e21fbc868e4b6891279d19b2be7c1faef583
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriterclosenamespace-method"></a><span data-ttu-id="b9b97-102">ISymUnmanagedWriter::CloseNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="b9b97-102">ISymUnmanagedWriter::CloseNamespace Method</span></span>
<span data-ttu-id="b9b97-103">Den zuletzt geöffneten schließt Namespace.</span><span class="sxs-lookup"><span data-stu-id="b9b97-103">Closes the most recently opened namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9b97-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b9b97-104">Syntax</span></span>  
  
```  
HRESULT CloseNamespace();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b9b97-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b9b97-105">Return Value</span></span>  
 <span data-ttu-id="b9b97-106">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="b9b97-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9b97-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b9b97-107">Requirements</span></span>  
 <span data-ttu-id="b9b97-108">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b9b97-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9b97-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9b97-109">See Also</span></span>  
 [<span data-ttu-id="b9b97-110">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b9b97-110">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="b9b97-111">OpenNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="b9b97-111">OpenNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)
