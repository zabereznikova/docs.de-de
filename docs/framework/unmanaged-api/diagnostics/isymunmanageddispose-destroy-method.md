---
title: ISymUnmanagedDispose::Destroy-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 51d2f0aedffdd88974a8184954ecbb9a231b70c6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939944"
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="d7ee4-102">ISymUnmanagedDispose::Destroy-Methode</span><span class="sxs-lookup"><span data-stu-id="d7ee4-102">ISymUnmanagedDispose::Destroy Method</span></span>
<span data-ttu-id="d7ee4-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span><span class="sxs-lookup"><span data-stu-id="d7ee4-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7ee4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d7ee4-104">Syntax</span></span>  
  
```  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d7ee4-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d7ee4-105">Return Value</span></span>  
 <span data-ttu-id="d7ee4-106">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="d7ee4-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7ee4-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d7ee4-107">Requirements</span></span>  
 <span data-ttu-id="d7ee4-108">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d7ee4-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7ee4-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7ee4-109">See also</span></span>

- [<span data-ttu-id="d7ee4-110">ISymUnmanagedDispose-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d7ee4-110">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)
