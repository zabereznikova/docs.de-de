---
title: ISymUnmanagedScope::GetEndOffset-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedScope::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 1d0b15c9-8059-435f-9fce-346a08b9bd36
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 739398d8c20f58d8b5e458e2de4cbb6f56c50fd8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624164"
---
# <a name="isymunmanagedscopegetendoffset-method"></a><span data-ttu-id="14ba4-102">ISymUnmanagedScope::GetEndOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="14ba4-102">ISymUnmanagedScope::GetEndOffset Method</span></span>
<span data-ttu-id="14ba4-103">Ruft den Endoffset für diesen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="14ba4-103">Gets the end offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14ba4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="14ba4-104">Syntax</span></span>  
  
```  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="14ba4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="14ba4-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="14ba4-106">[out] Ein Zeiger auf eine `ULONG32` , empfängt den Endoffset.</span><span class="sxs-lookup"><span data-stu-id="14ba4-106">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14ba4-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="14ba4-107">Return Value</span></span>  
 <span data-ttu-id="14ba4-108">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="14ba4-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14ba4-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="14ba4-109">Requirements</span></span>  
 <span data-ttu-id="14ba4-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="14ba4-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14ba4-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14ba4-111">See also</span></span>
- [<span data-ttu-id="14ba4-112">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="14ba4-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="14ba4-113">GetStartOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="14ba4-113">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)
