---
title: ISymUnmanagedScope::GetStartOffset-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetStartOffset method [.NET Framework debugging]
ms.assetid: da6bbc75-94d1-4354-9722-0d455b4428fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 19d116825efc4eb2ec1de22f232f46f8fb0fdf18
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425910"
---
# <a name="isymunmanagedscopegetstartoffset-method"></a><span data-ttu-id="7a8e3-102">ISymUnmanagedScope::GetStartOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="7a8e3-102">ISymUnmanagedScope::GetStartOffset Method</span></span>
<span data-ttu-id="7a8e3-103">Ruft den Anfangsoffset für diesen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="7a8e3-103">Gets the start offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a8e3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7a8e3-104">Syntax</span></span>  
  
```  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7a8e3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7a8e3-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="7a8e3-106">[out] Ein Zeiger auf eine `ULONG32` , die den Anfangsoffset enthält.</span><span class="sxs-lookup"><span data-stu-id="7a8e3-106">[out] A pointer to a `ULONG32` that contains the starting offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7a8e3-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7a8e3-107">Return Value</span></span>  
 <span data-ttu-id="7a8e3-108">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="7a8e3-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a8e3-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7a8e3-109">Requirements</span></span>  
 <span data-ttu-id="7a8e3-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7a8e3-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a8e3-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a8e3-111">See Also</span></span>  
 [<span data-ttu-id="7a8e3-112">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7a8e3-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 [<span data-ttu-id="7a8e3-113">GetEndOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="7a8e3-113">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)
