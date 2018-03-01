---
title: ISymUnmanagedDispose::Destroy-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedDispose.Destroy
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDispose::Destroy
helpviewer_keywords:
- ISymUnmanagedDispose::Destroy method [.NET Framework debugging]
- Destroy method [.NET Framework debugging]
ms.assetid: a854ab9f-d2ba-470e-867f-808c1e7bd07a
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8d418bbb476fea306bf9ad92ce2b30d558627009
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="b158c-102">ISymUnmanagedDispose::Destroy-Methode</span><span class="sxs-lookup"><span data-stu-id="b158c-102">ISymUnmanagedDispose::Destroy Method</span></span>
<span data-ttu-id="b158c-103">Bewirkt, dass das zugrunde liegende Objekt alle internen Verweise freigeben und Fehler für alle nachfolgenden Methodenaufrufe zurück.</span><span class="sxs-lookup"><span data-stu-id="b158c-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b158c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b158c-104">Syntax</span></span>  
  
```  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b158c-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b158c-105">Return Value</span></span>  
 <span data-ttu-id="b158c-106">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="b158c-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b158c-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b158c-107">Requirements</span></span>  
 <span data-ttu-id="b158c-108">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b158c-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b158c-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b158c-109">See Also</span></span>  
 [<span data-ttu-id="b158c-110">ISymUnmanagedDispose-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b158c-110">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)
