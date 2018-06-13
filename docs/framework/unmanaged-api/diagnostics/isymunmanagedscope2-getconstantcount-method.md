---
title: ISymUnmanagedScope2::GetConstantCount-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstantCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstantCount
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstantCount method [.NET Framework debugging]
- GetConstantCount method [.NET Framework debugging]
ms.assetid: 1e1f0be6-c4e8-4d6c-98cd-d5fa9f686e87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fbe41a3102a61052b2eceae7ccce3b93fd1bef6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426100"
---
# <a name="isymunmanagedscope2getconstantcount-method"></a><span data-ttu-id="92681-102">ISymUnmanagedScope2::GetConstantCount-Methode</span><span class="sxs-lookup"><span data-stu-id="92681-102">ISymUnmanagedScope2::GetConstantCount Method</span></span>
<span data-ttu-id="92681-103">Ruft die Anzahl der in diesem Bereich definierten Konstanten ab.</span><span class="sxs-lookup"><span data-stu-id="92681-103">Gets a count of the constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92681-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="92681-104">Syntax</span></span>  
  
```  
HRESULT GetConstantCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="92681-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="92681-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="92681-106">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe in Zeichen des Puffers benötigt, damit die Konstanten enthalten.</span><span class="sxs-lookup"><span data-stu-id="92681-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="92681-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="92681-107">Return Value</span></span>  
 <span data-ttu-id="92681-108">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="92681-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92681-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="92681-109">Requirements</span></span>  
 <span data-ttu-id="92681-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="92681-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92681-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92681-111">See Also</span></span>  
 [<span data-ttu-id="92681-112">ISymUnmanagedScope2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="92681-112">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
