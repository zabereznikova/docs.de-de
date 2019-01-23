---
title: ISymUnmanagedWriter3::Commit-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3.Commit
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3::Commit
helpviewer_keywords:
- Commit method, ISymUnmanagedWriter3 interface [.NET Framework debugging]
- ISymUnmanagedWriter3::Commit method [.NET Framework debugging]
ms.assetid: f6961922-46ec-4d2c-8369-85f880731f37
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 90ef45650b30fd57fb93d0e16eac6e34079745b1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54526235"
---
# <a name="isymunmanagedwriter3commit-method"></a><span data-ttu-id="f82e1-102">ISymUnmanagedWriter3::Commit-Methode</span><span class="sxs-lookup"><span data-stu-id="f82e1-102">ISymUnmanagedWriter3::Commit Method</span></span>
<span data-ttu-id="f82e1-103">Übernimmt die Änderungen, die bisher in den Stream geschrieben.</span><span class="sxs-lookup"><span data-stu-id="f82e1-103">Commits the changes written so far to the stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f82e1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f82e1-104">Syntax</span></span>  
  
```  
HRESULT Commit();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f82e1-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f82e1-105">Return Value</span></span>  
 <span data-ttu-id="f82e1-106">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="f82e1-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f82e1-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f82e1-107">Requirements</span></span>  
 <span data-ttu-id="f82e1-108">**Header:** CorSym.idl , CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f82e1-108">**Header:** CorSym.idl , CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f82e1-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f82e1-109">See also</span></span>
- [<span data-ttu-id="f82e1-110">ISymUnmanagedWriter3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f82e1-110">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
