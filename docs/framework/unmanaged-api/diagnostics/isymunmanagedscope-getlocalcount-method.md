---
title: ISymUnmanagedScope::GetLocalCount-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocalCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocalCount
helpviewer_keywords:
- GetLocalCount method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocalCount method [.NET Framework debugging]
ms.assetid: 3ede8fb5-f655-4088-8e19-9c53812588a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2f8dde609f83a0bbf040ce0e8a4f164259e8584a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427926"
---
# <a name="isymunmanagedscopegetlocalcount-method"></a><span data-ttu-id="31980-102">ISymUnmanagedScope::GetLocalCount-Methode</span><span class="sxs-lookup"><span data-stu-id="31980-102">ISymUnmanagedScope::GetLocalCount Method</span></span>
<span data-ttu-id="31980-103">Ruft die Anzahl der in diesem Bereich definierten lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="31980-103">Gets a count of the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31980-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="31980-104">Syntax</span></span>  
  
```  
HRESULT GetLocalCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="31980-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="31980-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="31980-106">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Anzahl der lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="31980-106">[out] A pointer to a `ULONG32` that receives the count of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="31980-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="31980-107">Return Value</span></span>  
 <span data-ttu-id="31980-108">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="31980-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31980-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="31980-109">Requirements</span></span>  
 <span data-ttu-id="31980-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="31980-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31980-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31980-111">See Also</span></span>  
 [<span data-ttu-id="31980-112">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31980-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
