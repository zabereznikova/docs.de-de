---
title: ISymUnmanagedMethod::GetScopeFromOffset-Methode
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
- ISymUnmanagedMethod.GetScopeFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetScopeFromOffset
helpviewer_keywords:
- GetScopeFromOffset method [.NET Framework debugging]
- ISymUnmanagedMethod::GetScopeFromOffset method [.NET Framework debugging]
ms.assetid: d14cf210-81f8-46e1-8b19-6ddec0ba8b11
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 890fd702bc2edb5714dc9c91a618c6420a11a27a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedmethodgetscopefromoffset-method"></a><span data-ttu-id="c9618-102">ISymUnmanagedMethod::GetScopeFromOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="c9618-102">ISymUnmanagedMethod::GetScopeFromOffset Method</span></span>
<span data-ttu-id="c9618-103">Ruft den umfassendsten lexikalischen Gültigkeitsbereich innerhalb dieser Methode, die den angegebenen Offset einschließt.</span><span class="sxs-lookup"><span data-stu-id="c9618-103">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span> <span data-ttu-id="c9618-104">Dies kann verwendet werden, um die lokalen Variablen starten.</span><span class="sxs-lookup"><span data-stu-id="c9618-104">This can be used to start local variable searches.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9618-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c9618-105">Syntax</span></span>  
  
```  
HRESULT GetScopeFromOffset(  
    [in]  ULONG32 offset,  
    [out, retval] ISymUnmanagedScope**  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c9618-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="c9618-106">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="c9618-107">[in] Ein `ULONG` , der den Offset enthält.</span><span class="sxs-lookup"><span data-stu-id="c9618-107">[in] A `ULONG` that contains the offset.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="c9618-108">[out] Ein Zeiger, der festgelegt wird, wird auf das zurückgegebene [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c9618-108">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c9618-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c9618-109">Return Value</span></span>  
 <span data-ttu-id="c9618-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="c9618-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9618-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c9618-111">Requirements</span></span>  
 <span data-ttu-id="c9618-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c9618-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9618-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9618-113">See Also</span></span>  
 [<span data-ttu-id="c9618-114">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c9618-114">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
