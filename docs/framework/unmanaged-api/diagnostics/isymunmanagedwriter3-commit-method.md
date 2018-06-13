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
ms.openlocfilehash: 9e4e2cd49bdffd0a1293a5601cb44e4804e2b1ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428953"
---
# <a name="isymunmanagedwriter3commit-method"></a><span data-ttu-id="ca135-102">ISymUnmanagedWriter3::Commit-Methode</span><span class="sxs-lookup"><span data-stu-id="ca135-102">ISymUnmanagedWriter3::Commit Method</span></span>
<span data-ttu-id="ca135-103">Führt einen Commit der Änderungen, die bisher in den Stream geschrieben.</span><span class="sxs-lookup"><span data-stu-id="ca135-103">Commits the changes written so far to the stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca135-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ca135-104">Syntax</span></span>  
  
```  
HRESULT Commit();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ca135-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ca135-105">Return Value</span></span>  
 <span data-ttu-id="ca135-106">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="ca135-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca135-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ca135-107">Requirements</span></span>  
 <span data-ttu-id="ca135-108">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ca135-108">**Header:** CorSym.idl , CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca135-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca135-109">See Also</span></span>  
 [<span data-ttu-id="ca135-110">ISymUnmanagedWriter3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ca135-110">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
